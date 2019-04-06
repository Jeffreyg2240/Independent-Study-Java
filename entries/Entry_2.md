### Week 2:
<br>
**JDK**: Java Development Kit
System.out.print vs System.out.println
System.out.println line breaks for the characters, System.out.print doesn’t.
Outputs and strings can be concatanted using “+”
```java
String username = "PrinceNelson";
System.out.println("Your username is: " + username);
// Your username is: PrinceNelson


```
Just like python, ruby and JS, Java uses the same or similar symbols for math and conditionals

System.out.print vs System.out.println
.equals if two strings are equal to each other
```java
+
- 
*
/
%
++
--
-=
+=
=
==
<=
>=
&&
||
String person1 = "Paul";
String person2 = "John";
String person3 = "Paul";

System.out.println(person1.equals(person2));
//prints false, since "Paul" is not "John"

System.out.println(person1.equals(person3));
//prints true, since "Paul" is "Paul"
```

#### Object Orientation Basics: Java
The void keyword (which means “completely empty”) indicates to the method that no value is returned after calling that method.
static means that the method is associated with the class, not a specific instance (object) of that class. This means that you can call a static method without creating an object of the class.
void means that the method has no return value.
Int would signify for the method to return a integer.

**Look a the comments**

```java
public class Store {
  // new method: constructor!, public Store is like a class function and will wait until it is called on.
  public Store() {
  }
  //kind of like ‘def initialize’ in Ruby
  public static void main(String[] args) {
  }
}
```



Very similar to Ruby’s OO.
```java
public class Car {
  String color;
  // new fields!
  boolean isRunning;
  int velocity;
  // new parameters that correspond to the new fields
  public Car(String carColor, boolean carRunning, int milesPerHour) {
    color = carColor;
    // assign new parameters to the new fields
    isRunning = carRunning;
    velocity = milesPerHour;
  }
  public static void main(String[] args) {
    // new values passed into the method call
    Car ferrari = new Car("red", true, 27);
    Car renault = new Car("blue", false, 70);
    renault.isRunning;
    // false
    ferrari.velocity;
    // 27
  }
}
```

```java
public class Dog {
  String breed;
  boolean hasOwner;
  int age;
  public Dog(String dogBreed, boolean dogOwned, int dogYears) {
    System.out.println("Constructor invoked!");
    breed = dogBreed;
    hasOwner = dogOwned;
    age = dogYears;
  }
  public static void main(String[] args) {
    System.out.println("Main method started");
    Dog fido = new Dog("poodle", false, 4);
    Dog nunzio = new Dog("shiba inu", true, 12);
    boolean isFidoOlder = fido.age > nunzio.age;
    int totalDogYears = nunzio.age + fido.age;
    System.out.println("Two dogs created: a " + fido.breed + " and a " + nunzio.breed);
    System.out.println("The statement that fido is an older dog is: " + isFidoOlder);
    System.out.println("The total age of the dogs is: " + totalDogYears);
    System.out.println("Main method finished");
  }
}
/*
Main method started
Constructor invoked!
Constructor invoked!
Two dogs created: a poodle and a shiba inu
The statement that fido is an older dog is: false
The total age of the dogs is: 16
Main method finished

*/
```
String.format(“%.2f”, any double) is used to limit the decimal point to two places; 

<br>
After finishing Codecademy, I started working on Udemy's Java course, after a while of structured learning I decided to roam freely and revisit documentations. In the past, I remember being interested in BCIs, so I decided to look up what BCI implantations are within Java thus far. I ended up not finding much, as it was much more popular in Python. After browsing through countless documentations I came upon an eye-tracking program, JGazed based in Java. I ended up looking deeper into the documentation and might work on a game surrounding it for my independent study program.
#### Takeaways. 
Java’s math and conditions and loops are really similar to the other languages we’ve learned, meaning, if you learning one thing somewhere, don’t forget it, you can always apply it elsewhere, especially when it comes to mathematics, science, and programming languages.
<br>Also remember to take notes to everything you learn, especially from documentations, because most brains cannot retain all the information after hours of browsing.<br><br>**“sysout”** is abbreviation for **“System.out.println”**.

<b>[&larr; Back](Entry_1.md)  | [Next &rarr;](Entry_3.md) | [README](../README.md)</b>