### Week 1:

During the first week of independent study, I explored through my options, my initial thought was something along the lines of python ML, but I didn't know what I wanted to make of it.
<br>

This lead me to recount my options again and I went with one of the most practices languages in Computer Science classes - Java.
<br>
Along with Wei and Johnson, my group members we decided to make a game, but couldn’t conclude which game to make. To fond upon the idea of making something like <b>‘Pokemon’</b>, but this has yet to be decided. In the meantime we went online and started to take tutorials with Coursera, Codecademy, etc. My current goal is to finish the Codecademy Java tutorial and move towards the Coursera courses.
<br>
<b>JVM - Java Virtual Machine</b><br>
So far, I’ve found it helpful looking at other people’s project and try to understand their code whether be a video or repository.  I started by looking at other’s repository of the game ‘tetris’ and found some basic blocks in their code to research - private and public. In doing so I found the the [4 access modifiers in Java](https://www.geeksforgeeks.org/access-modifiers-java/). 
<br>

Private vs Protected vs Public vs Packaged
* Private: The most restricted access modifiers (The highest level class). It can only be accessed within it's own class. No other package will be able to access it.

```java
//Java program to illustrate error while 
//using class from different package with 
//private modifier 
package p1; 

class A 
{ 
private void display() 
	{ 
		System.out.println("GeeksforGeeks"); 
	} 
} 

class B 
{ 
public static void main(String args[]) 
	{ 
		A obj = new A(); 
		//trying to access private method of another class 
		obj.display(); 
	} 
} 

```
* Protected: It can be accessed within the same or sub package.

```java
//Java program to illustrate 
//protected modifier 
package p1; 

//Class A 
public class A 
{ 
protected void display() 
	{ 
		System.out.println("GeeksforGeeks"); 
	} 
} 

```
* Public: Just like global variables in Ruby, try to avoid making them as much as possible(they aren’t good practice in Java.)
```java
//Java program to illustrate 
//public modifier 
package p1; 
public class A 
{ 
public void display() 
	{ 
		System.out.println("GeeksforGeeks"); 
	} 
} 
package p2; 
import p1.*; 
class B 
{ 
	public static void main(String args[]) 
	{ 
		A obj = new A; 
		obj.display(); 
	} 
} 

```
* Packaged: Also known as the default modifier 
```java
//Java program to illustrate default modifier 
package p1; 

//Class Geeks is having Default access modifier 
class Geek 
{ 
	void display() 
	{ 
		System.out.println("Hello World!"); 
	} 
} 


```

<br><img src="https://github.com/Jeffreyg2240/Independent-Study-Java/blob/master/images/4ps.PNG?raw=true">
<br><img src="https://github.com/Jeffreyg2240/Independent-Study-Java/blob/master/images/4psv2.PNG?raw=true"><br>
Unlike Ruby or Python in Java you have to declare a variable 
```java
// doubles holds floats
double price = 1.99;
// int hold integers, whole numbers
int price = 2;
// boolean holds true or false; 1 or 0
boolean isEmployed = 0;
// String holds inpuis, either numbers, letters, symbols, etc, but they cannot be 
String name - "Bob Ross";
// char holds 1 character, either Symbols, Integers, or Letters
char grade = 'F';
char firstLetter = 'p';
char punctuation = '!';
// if char has more than 1 letter it will return a error
char grade = '+F';

```
<b>*Note* Semi-colon is very important in Java<br><br>'' and "" makes the difference between spending passing and spending 20 minutes to find out the error in Codecademy.
<br><br>In Ruby we run the code with 'ruby &lt;filename&gt;.rb, but in Java it's javac &lt;filename&gt;.java</b><br>
<br>Currently I am just tinkering around with the online repository and trying to understand them, but I don't have a planned out next step apart from doing the online courses.

<b>[Next &rarr;](Entry_2.md) | [README](../README.md)</b>