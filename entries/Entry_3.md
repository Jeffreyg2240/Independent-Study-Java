### Week 3:
During week 3, I decided to move away from Udemy for a bit and learn by myself, although I often took the challenge problems from Udemy and tested it on <b>IntelliJ</b> which is a Jave IDE.
<br>
At first I started to learn about arrays then moved towards reading user inputs, like if like "get.chomp" in Ruby. Afterwards I learned how to <i>"parse"</i> an array meaning turning it from a string to a integer, to a double, and vice versa.
<br>While testing it out I found that if I tried to parse an string that contained alphabets or symbols into a double or integer, the code would fail to run.
<br><br>*** Note look at the comments of the code for description and explanation. ***
```java
//Break
 for (int i = 0; i < 10; i++) {
  if (i == 4) {
    break;
  }
  System.out.println(i);
} 
0
1
2
3
//Continue 
for (int i = 0; i < 10; i++) {
  if (i == 4) {
    continue;
  }
  System.out.println(i);
} 
0
1
2
3
4
5
6
7
8
9

```

Arrays in Java: 
```java
// You don’t have to declare cars as string, it can also be boolean, char, int, or any other data type within Java.
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
// You use <b>curly brackets “{}”</b> to declare arrays instead of <b>brackets “[]”</b>
System.out.println(cars[0]);
//Will print Volvo
cars[0] = "Opel";
System.out.println(cars[0]);
//Volvo has been replaced by Opel, thus Opel will appear on the screen.
System.out.println(cars.length);
//4


```
Declaring arrays within array
<b>Also remember that arrays also start at 0.</b>
```java
int[][] commonDigits = {{},{}};
commonDigits[0][0] = int 5;
// {{5},{}}
commonDigits[0][1] = int 4;
commonDigits[0][2] = int 12;
commonDigits[1][0] = int 54;
// {{5, 4, 12},{54}}
```
.parse.int will convert a string or char or boolean into a integer. This will only work whatever is being converted is a number, if it contains a symbol or letter, an error will appear.

```java
String number = "10";
int result = Integer.parseInt(number);	
number += 1
result += 1;		
System.out.println(result);
//11
System.out.println(number);
//101
int resultInDouble = Double.parseDouble(result);	
System.out.println(resultInDouble);
//11.0
```
As you can see this works for most of the major data types for Java like <b>char, long, int, String, and double.</b>

#### Scanner class
<br>Scanner is a built-in class within Java to get user input<br>
You usually want to parse the user input because for the most part, they’re strings.
Scanner is a built-in class within Java to get user input
```java
Scanner scanner = new.Scanner(print.in);
//Returns true of false depending on if the number entered is an int;
scanner.nextLine();
boolean isAnInt = scanner.hasNextInt();
//All scanners need a scanner close to declare that the scanner is finished so that it can be redeclared. It is like a private class, scanner variable is not saved buy isAnAnt is.
scanner.close();

//Example:
//takes what every the user types in the next line as the user name
System.out.println("Enter your username: "); 
Scanner scanner = new Scanner(System.in); 
String username = scanner.nextLine(); 
System.out.println("Your username is " + username);

```

#### Creating JFrame
<br>
Although <b>Udemy</b> doesn’t teach <b>JFrame</b> until much later, I’ve decided to look at other documentation based around it.

The frame is an instance of the JFrame class, which opens a window with text-decorations such as borders, title, and buttons. 
** GUIs usually contain 1 or more frame or panels**
<img src='https://github.com/Jeffreyg2240/Independent-Study-Java/blob/master/images/jframe3.JPG?raw=true'>
Here is an example of a button in a frame<br>
<img src = 'https://github.com/Jeffreyg2240/Independent-Study-Java/blob/master/images/jf2.JPG?raw=true' width = '1200px'>
<img src = 'https://github.com/Jeffreyg2240/Independent-Study-Java/blob/master/images/jframe.JPG?raw=true' width = '1200px'>

<a href = “https://javatutorial.net/swing-jframe-basics-create-jframe”>Creating JFrame</a><br>
<b>JFrame()</b>: creates a frame which is invisible<br>
<b>JFrame(GraphicsConfiguration gc)</b>: creates a frame with a blank title and graphics configuration of screen device.<br>
<b>JFrame(String title)</b>: creates a JFrame with a title.<br>
<b>JFrame(String title, GraphicsConfiguration gc)</b>: creates a JFrame with specific Graphics configuration and specified title.<br>

I’ve been still tinkering around with JFrame, but most of the code is confusing and I’m learning as I go. During the weekend I’ve moved back towards <b>Udemy</b> and working more on the courses until I come upon JFrame.
Although <b>Udemy</b> doesn’t teach JFrame until much later, I’ve decided to look at other documentation based around it.
#### Takeaways: 


Takeaways, depending on what IDE you are using, sometimes the files will be <b>‘import’</b>ed for you.
```java
import java.awt.*;
import javax.swing.*;

```
<br>
Don't always go to ahead or else you will get stuck, pace your learning evenly.


<b>[&larr; Back](Entry_2.md)  | [Next &rarr;](Entry_4.md) | [README](../README.md)</b>