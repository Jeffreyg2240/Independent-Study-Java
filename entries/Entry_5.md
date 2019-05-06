### Week 5:
During week 5 of Java exploration, I continued my progress of week 4 exploring with new game ideas and tutorials, last week I made brick breaker in Java, and this week I made Snake in Java.
<br><br>There were some challenging parts, especially restricting the snake from traveling backward, since it’s going left and then turns right it’ll bump into itself and lose, the same with up and down.
Here is how to import images or graphics in Java,
```java
ImageFrame frame = new ImageFrame("filepath");
//or
ImageIcon frame = new ImageIcon("filepath");
```
 
I have been using ImageIcon only so I don't know how ImageFrame operates.
### 2D Graphics Java
This is a continuation of what I was studying last week, I was waiting until I had more experience with it before putting into my blog entry.
* **.repaint**  <br>
 This removed the previous graphics and imports the new graphics, paint is the 2D graphics from functions like draw, drawRect, drawOval, etc, and repaint updates the animation in cases of when it translates to somewhere else within the screen.
* **.dispose**
 causes the JFrame window to be destroyed and cleaned up by the operating system

These are self explanatory
* **setCurve(x1, y1, ctrlx1, ctrly1, ctrlx2, ctrly2, x2, y2);**
* **draw(new Line2D.Double(x1, y1, x2, y2));**

* **drawRect(x ,y ,width ,height );**
* **drawOval(x ,y ,width ,height );**
* **drawString(“String”,x,y);**
* **fillRect(x ,y ,width, height);** (fill can fill the the shape with a certain color using **"setColor(Color.COLOR)"**)
* **draw(new Line2D.Double(x1, y1, x2, y2));**

<hr>
Here is a gif of the snake game I used, I found most of the graphics online, the target, snake head, and body are all 25x25 pixels.
<br>
<br><img src="https://github.com/Jeffreyg2240/Independent-Study-Java/blob/master/images/SnakeR.gif?raw=true" width=200% height=200%>
<br><font size="2" color="gray">(Yes, I got "his" permission)</font><br>
*I forgot to put in what happens when space is clicked, so here it is
<img src = "https://github.com/Jeffreyg2240/Independent-Study-Java/blob/master/images/replay.JPG?raw=true">
<hr>
#### Takeaways:

Sometimes problems will be much easier if you backtrack your steps. I had trouble finding a way to prevent the snake from reversing its direction. I went into making complicated for loops, but could barely get it to work. I took a break and started my problem from scratched and approached it with a broader mindset and was able to use simple conditions to solve my problem.

##### Notes:
When creating an array in Java, if you want to use the .length method, you must declare the length at the beginning, thus if it goes over the length that it's been declared with, there will be a error.
<br><br>Both __this__ and __super__ are known as calls.
“__super__” is used to access the parent class methods, while “__this__” is used to call the current class members.(__variables__ and __methods__)


<br><b>[&larr; Back](Entry_4.md)  | [Next &rarr;](Entry_6.md) | [README](../README.md)</b>

<br><br>Here is the Snake game project<br>
#### Main class(JFrame Setup)
```java
import javax.swing.*;
        import java.awt.*;

public class Main {
    public static void main(String[] args){
        JFrame frame = new JFrame();
        Gameplay gameplay = new Gameplay();
        frame.setBounds(50,50,905,700);
        frame.setResizable(false);
        frame.setBackground(Color.DARK_GRAY);
        frame.setVisible(true);
        frame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        frame.add(gameplay);
    }
}

```
#### Gameplay class
```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.util.Random;

public class Gameplay extends JPanel implements KeyListener, ActionListener {

    private ImageIcon titleImage;
    //the animations of the snake
    private ImageIcon rightm;
    private ImageIcon leftm;
    private ImageIcon upm;
    private ImageIcon downm;
    private ImageIcon snakeimage;
    private ImageIcon food;
    //choosing a random X and Y position for the food
    private Random random = new Random();
    private int xpos = random.nextInt(34);
    private int ypos = random.nextInt(23);

    private int[] snakeLengthX = new int[750];
    private int[] snakeLengthY = new int[750];
    private boolean left = false;
    private boolean right = false;
    private boolean up = false;
    private boolean down = false;
    private boolean play = false;
    private int score = 0;
    private int snakeLength = 3;
    private int moves = 0;
    //Enables the game to start with a time function
    private Timer time;
    //The length of the array for all possible x and y positions on the graph
    private int[] enemyxpos = new int[35];
    private int[] enemyypos = new int[24];
    //milliseconds
    private int delay = 100;
    public Gameplay(){
        addKeyListener(this);
        setFocusable(true);
        setFocusTraversalKeysEnabled(false);
        time = new Timer(delay,this);
        time.start();
    }
    public void paint(Graphics g){
        //Plots out all possible points for the snake to move towards, since the snake travels in increments of 25, the food will spawn in increments of 25 x and y.
        for(int i= 1;i<=850/25;i++) {
            enemyxpos[i - 1] = i * 25;
        }
        for(int i=1;i<=575/25;i++) {
            enemyypos[i - 1] = i * 25+50;
        }
        //default/starting position for the snake
        if (moves == 0){
            //Not the length but the position of the length
            snakeLengthX[0] = 100;
            snakeLengthX[1]=75;
            snakeLengthX[2]=50;
            snakeLengthY[0] = 100;
            snakeLengthY[1]=100;
            snakeLengthY[2]=100;
        }
        g.setColor(Color.white);
        g.drawRect(24,10, 851, 55);
        titleImage = new ImageIcon("src/snaketitle.jpg");
        titleImage.paintIcon(this,g,  25, 11);
        g.setColor(Color.white);
        g.drawRect(24,74, 851,577);
        g.setColor(Color.black);
        g.fillRect(25,75,850,575);
        //display score
        g.setColor(Color.white);
        g.setFont(new Font("times new roman", Font.PLAIN, 14));
        g.drawString("Score: " + score,780,30);
        g.drawString("Length: " + snakeLength,780,50);
        g.setFont(new Font("times new roman", Font.PLAIN, 18));
        g.drawString("Press space to begin or play again",35,35);
        //The starting Image will be the snake head pointing right
        rightm = new ImageIcon("src/rightmouth.png");
        //The first part of the snake, head, which is the first number in the array which is 750,750, the starting position.
        rightm.paintIcon(this,g,snakeLengthX[0],snakeLengthY[0]);
        //This to to animate the head when it turns and the rest of the body
        for (int i=0; i<snakeLength;i++){

            if (i==0 && right){
                rightm = new ImageIcon("src/rightmouth.png");
                //The first part of the snake, head, which is the first number in the array which is 750,750, the starting position.
                rightm.paintIcon(this,g,snakeLengthX[i],snakeLengthY[i]);
            }
            if (i==0 && left){
                leftm = new ImageIcon("src/leftmouth.png");
                //The first part of the snake, head, which is the first number in the array which is 750,750, the starting position.
                leftm.paintIcon(this,g,snakeLengthX[i],snakeLengthY[i]);
            }
            if (i==0 && up){
                upm = new ImageIcon("src/upmouth.png");
                //The first part of the snake, head, which is the first number in the array which is 750,750, the starting position.
                upm.paintIcon(this,g,snakeLengthX[i],snakeLengthY[i]);
            }
            if (i==0 && down){
                downm = new ImageIcon("src/downmouth.png");
                //The first part of the snake, head, which is the first number in the array which is 750,750, the starting position.
                downm.paintIcon(this,g,snakeLengthX[i],snakeLengthY[i]);
            }
            if (i!=0){
                snakeimage= new ImageIcon("src/snakeimage.png");
                snakeimage.paintIcon(this,g,snakeLengthX[i],snakeLengthY[i]);
            }
        }
        food = new ImageIcon("src/wei.png");
        //Once the head of the snake meets with the food, a new position of food is chosen and the length of the snake lengthens
        if(enemyxpos[xpos] == snakeLengthX[0] && enemyypos[ypos] == snakeLengthY[0]){
            snakeLength++;
            score+=100;
            xpos = random.nextInt(34);
            ypos = random.nextInt(23);
        }

        food.paintIcon(this,g,enemyxpos[xpos],enemyypos[ypos]);

        for(int i = 1; i<snakeLength; i++){
            if(snakeLengthX[i]==snakeLengthX[0] && snakeLengthY[i] == snakeLengthY[0]){
                    right=false;
                    left=false;
                    up=false;
                    down=false;
                    play=false;
                    g.setColor(Color.white);
                    g.setFont(new Font("times new roman", Font.PLAIN, 50));
                    g.drawString("Game Over", 300,300);
                    g.setFont(new Font("times new roman", Font.PLAIN, 20));
                    g.drawString("Press space to play again", 330,330);

            }
        }
    }
    //@Override
    public void actionPerformed(ActionEvent e){
        if(play) {
            time.start();
            if (right) {
                //This will ensure the snake body to follow the head by taking the position of the piece before it
                for (int i = snakeLength - 1; i >= 0; i--) {
                    snakeLengthY[i + 1] = snakeLengthY[i];
                }
                for (int i = snakeLength; i >= 0; i--) {
                    if (i == 0) {
                        snakeLengthX[i] = snakeLengthX[i] + 25;
                    } else {
                        snakeLengthX[i] = snakeLengthX[i - 1];
                    }
                    //Moving pass borders, hits x border comes out the over side of the x border.
                    if (snakeLengthX[i] > 850) {
                        snakeLengthX[i] = 25;
                    }
                }
            }
            if (left) {
                //This will ensure the snake body to follow the head by taking the position of the piece before it
                for (int i = snakeLength - 1; i >= 0; i--) {
                    snakeLengthY[i + 1] = snakeLengthY[i];
                }
                for (int i = snakeLength; i >= 0; i--) {
                    if (i == 0) {
                        snakeLengthX[i] = snakeLengthX[i] - 25;
                    } else {
                        snakeLengthX[i] = snakeLengthX[i - 1];
                    }
                    //Moving pass borders, hits x border comes out the over side of the x border.
                    if (snakeLengthX[i] < 25) {
                        snakeLengthX[i] = 850;
                    }
                }
            }
            if (down) {
                //This will ensure the snake body to follow the head by taking the position of the piece before it
                for (int i = snakeLength - 1; i >= 0; i--) {
                    snakeLengthX[i + 1] = snakeLengthX[i];
                }
                for (int i = snakeLength; i >= 0; i--) {
                    if (i == 0) {
                        snakeLengthY[i] = snakeLengthY[i] + 25;
                    } else {
                        snakeLengthY[i] = snakeLengthY[i - 1];
                    }
                    //Moving pass borders, hits y border comes out the over side of the y border.
                    if (snakeLengthY[i] > 625) {
                        snakeLengthY[i] = 75;
                    }
                }
            }
            if (up) {
                //This will ensure the snake body to follow the head by taking the position of the piece before it
                for (int i = snakeLength - 1; i >= 0; i--) {
                    snakeLengthX[i + 1] = snakeLengthX[i];
                }
                for (int i = snakeLength; i >= 0; i--) {
                    if (i == 0) {
                        snakeLengthY[i] = snakeLengthY[i] - 25;
                    } else {
                        snakeLengthY[i] = snakeLengthY[i - 1];
                    }
                    //Moving pass borders, hits y border comes out the over side of the y border.
                    if (snakeLengthY[i] < 75) {
                        snakeLengthY[i] = 625;
                    }
                }
            }
            repaint();
        }
    }
    public void keyPressed(KeyEvent e){
        if(e.getKeyCode() == KeyEvent.VK_SPACE){
            right=true;
            left=false;
            up=false;
            down=false;
            moves = 0;
            score = 0;
            play=true;
            snakeLength=3;
            repaint();
        }
        if(e.getKeyCode() == KeyEvent.VK_RIGHT){
            moves++;
            /*
            This is prevent the snake from moving into itself,
             meaning it cannot collide with itself by moving in the opposite direction it is traveling in.
             (ie: Up cannot travel down, left cannot travel right, right cannot travel left, down cannot travel up)
             */
            right = true;
            if(!left){
                right=true;
            }else{
                right=false;
                left=true;
            }
            up=false;
            down=false;
        }
        if(e.getKeyCode() == KeyEvent.VK_LEFT){
            moves++;
            left = true;
            //when down key has not been pressed
            if(!right){
                left=true;
            }else{
                left=false;
                right=true;
            }
            up=false;
            down=false;
        }
        if(e.getKeyCode() == KeyEvent.VK_UP){
            moves++;
            up = true;
            if(!down){
                up=true;
            }else{
                up=false;
                down=true;
            }
            left=false;
            right=false;
        }
        if(e.getKeyCode() == KeyEvent.VK_DOWN){
            moves++;
            down = true;
            if(!up){
                down=true;
            }else{
                down=false;
                up=true;
            }
            left=false;
            right=false;
        }
    }
    //keyTyped and keyRealsed will not be used
    public void keyTyped(KeyEvent e){ }

    public void keyReleased(KeyEvent e){ }
    public static void main(String[] args){

    }

}

```