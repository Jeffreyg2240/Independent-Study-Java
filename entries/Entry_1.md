### Week 1:

During the first week of independent study, I explored through my options, my initial thought was something along the lines of python ML, but I didn't know what I wanted to make of it.
<br>

This lead me to recount my options again and I went with one of the most practices languages in Computer Science classes - Java.
<br>
Along with Wei and Johnson, my group members we decided to make a game, but couldn’t conclude which game to make. To fond upon the idea of making something like <b>‘Pokemon’</b>, but this has yet to be decided. In the meantime we went online and started to take tutorials with Coursera, Codecademy, etc. My current goal is to finish the Codecademy Java tutorial and move towards the Coursera courses.
<br>
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

<b>[Next &rarr;](Entry_2.md) | [README])(../README.md)</b>