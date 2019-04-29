### Week 4:
Almost halfway finished with independent study, 4th week in, but I’ve yet to decide on a project.	
On week 4, I reviewed the OO programming that I’ve learned on Codecademy on week 2.
<br>During Spring Break, I stopped on the Udemy lessons starting to watch videos on making basic Java GUIs and games, since we were basically half way past the finish line.
<br>Private can only see accessed by its own class, it's the most commonly used class.
<br>
#### .equals
<br>
.equals() check if 2 things are equal to each other either it being string, int, or boolean.
<br>This will return a boolean.<br>
In Java, string equals() method compares the two given strings based on the data/content of the string. If all the contents of both the strings are same then it returns true. If all characters are not matched then it returns false.
<br>We can use == operators for </b>reference comparison (address comparison)</b> and .equals() method for <b>content comparison</b>. In simple words, == checks if both objects point to the same memory location whereas .equals() evaluates to the comparison of values in the objects. [Source](https://www.geeksforgeeks.org/difference-equals-method-java/)
<br>
#### Timer:
When any variable is declared as a timer it has to container “Timer” in the front
```Java
Timer timer;
//or
Private Timer timer;
//Also delay could be any number and this is the current time
timer = new Timer(delay, this);
timer.start();
```
### 2nd Week
After doing a few activities and watching a few videos on Udemy I got tired and bored of the videos since I couldn’t ever see myself using anything that was taught, so I moved on to YouTube and watched tutorials on GUIs and basic game tutorials.



### JFrame Continued

##### .setBounds(x,y,width,height);
	Declare the position and size of the frame(windows page).
##### .getContentPane().setBackground(Color. COLOR); 
	Set the background color to any desired color but the name of the color has to be capitalized in some IDEs.
##### .setResizeable(true/false);
	Will prevent/allow the windows to be resized, it is true by default.
##### .setVisible(true/false);
	Will allow the user to see the JFrame/Window, this is set to false by default. It can be helpful to close the window temporarily instead of permanently.
##### .setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); or .setDefaultCloseOperation(JFrame.DO_NOTHING_ON_CLOSE);
	This is set on Exit on close by default but can be changed so that the close button doesn't work
##### .add(another class)
To call on another class within your current class, you use “.add”. Make sure the other class is defined in the beginning first. Thus the other class must have <b>“extend JPanel”</b> after the name of the class so it knows that it’s an addon to a JFrame.

```Java
private final JFrame frame = new JFrame();

private WindowAdapter getWindowAdapter() {
   return new WindowAdapter() {
       @Override
       public void windowClosing(WindowEvent we) {
           super.windowClosing(we);
           JOptionPane.showMessageDialog(frame, "Can’t Exit");
       }
       @Override
       public void windowIconified(WindowEvent we) {
           frame.setState(JFrame.NORMAL);
           JOptionPane.showMessageDialog(frame, "Can’t Minimize");
       }
   };

```
Sets it so when you try to click the x button or close the screen, a display will show up showing “Can’t Exit” and minimize will show “Can’t Minimize”.
This overrides the JFrame’s close and minimizes functions within Java.
### Notes:
<br>If you set something = **null**, it forces a error(crash).
<br>.toLowerCase & .toUpperCase are identical to Ruby’s lower and upper case methods
<br>Private is most commonly used to declare a variable that is within a class 
```Java
import javax.swing.*;
import java.awt.*;
```
You are importing the whole library from <b>javax.swing</b> and <b>java.awt</b> when you add the “*”
<br>This is the outcome so far of what I did with JFrame.
<br><img src = "">
<br>
### Notes:
<br>If you set something = **null**, it forces a error(crash).
<br>.toLowerCase & .toUpperCase are identical to Ruby’s lower and upper case methods
<br>Private is most commonly used to declare a variable that is within a class 
```java
import javax.swing.*;
import java.awt.*;
```
You are importing the whole library from <b>javax.swing</b> and <b>java.awt</b> when you add the “*”
<br>All Key event are written as:
```java
if(e.getKeyCode() == KeyEvent.VK_RIGHT){
   //Constraining method
   if(playerX >= 600) {
       playerX = 600;
   }else{
       moveRight();
   }

}
//Left Arrow Key
if(e.getKeyCode() == KeyEvent.VK_LEFT){
   //Constraining method
   if(playerX <= 10){
       playerX = 10;
   }else{
       moveLeft();
   }
}
if(e.getKeyCode() == KeyEvent.VK_ENTER){
  
}

```

### Takeaways
<br><b>You can’t force yourself to learn something you aren't motivated.</b> The Udemy videos were becoming tiring and I was dozing off while watching them, plus the progression was extremely slow and probably not everything taught will be used for my final product, so I resorted to YouTube videos.


<b>[&larr; Back](Entry_3.md)  | [Next &rarr;](Entry_5.md) | [README](../README.md)</b>