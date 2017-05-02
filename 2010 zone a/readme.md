# Zone A 2010 Answers

### Question 1

- a) The program will still be able to run as JVM will automatically call the default constructor instead.
- b)
```java
import java.awt.Color;
import java.awt.Graphics;
public class SolidEllipse{
  private int x;
  private int y;
  private int width;
  private int height;
  private Color color;
  public void fill(Graphics g){
    g.setColor(color);
    g.fillOval(x,y,width,height);
  }
  public int getX(){
    return x;
  }
  public void setX(int a){
    x = a;
  }
  public int getY(){
    return y;
  }
  public void setY(int a){
    y = a;
  }
  public int getWidth(){
    return width;
  }
  public void setWidth(int w){
    width = w;
  }
  public int getHeight(){
    return height;
  }
  public void setHeight(int h){
    height = h;
  }
  public Color getColor(){
    return color;
  }
  public void setColor(Color c){
    color = c;
  }
}
```
- c)
```java
public SolidEllipse(SolidElipse e){
  x = e.getX();
  y = e.getY();
  width = e.getWidth();
  height = e.getHeight();
  color = e.getColor();
}
```
- d)
```java
SolidEllipse
---------------------
x:int
y:int
width:int
height:int
color:color
---------------------
getX():int
getY():int
getWidth():int
getHeight():int
getColor():Color
setX(a:int)
setY(a:int)
setWidth(w:int)
setHeight(h:int)
setColor(c:Color)
```

### Question 2

- a) (i) local variables, methods
- a) (ii) objects, instance variables
- c) Yes, the unreachable object is BookObject1
- d) They become garbage collectible and their spaces will be used by other objects to be claimed.
- e) For an object to be eligible for garbage collectible and unreachable: all references to that object is out of scope, all references to the object are reassigned leaving no way of reaching the object, all references to the object is set to null, leaving no way to reach the object.
- f) (i) Variable *size* is scoped to the class *Life*
- f) (ii) Variable *s* is scoped within the *setSize()* method
- f) (iii) A

### Question 3

- a) No, Java does not allow multiple inheritance.
- b) The problem is JVM would not be able to know which *run()* method should be called.
- c)
```java
public class C extends H implements G{
  void hello(int n){
    System.out.println("Hello" + n);
  }
  void goodBye(int n){
    System.out.println("Goodbye" + n);
  }
}
```
- d) The purpose of overriding is to customise methods from parent class to suit the use of the child class.
- e)
```java
public static int add(int a, int b){
  return a+b;
}
```
- f)
```java
public int add(int a, int b, int c){
  return a+b+c;
}
```

### Question 4

- a)
```java
import java.awt.*;
import javax.swing.*;
public class MyGUI{
  JFrame frame;
  JPanel panel1;
  JPanel panel2;
  JButton button1;
  JButton button2;
  public static void main(String[]args){
    MyGUI gui = new MyGUI();
    gui.go();
  }
  public void go(){
    frame = new JFrame("Question 4");
    panel1 = new JPanel();
    button1 = new JButton("Click me");
    panel2 = new JPanel();
    button2 = new JButton("DON'T CLICK ME");
    panel1.add(button1);
    panel2.add(button2);
    frame.add(panel1, BorderLayout.CENTER);
    frame.add(panel2, BorderLayout.SOUTH);
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setSize(500,500);
    frame.setVisible(true);
  }
}
```
- b) as wide as the JFrame.
- c) *Let's finishe* only because finally block will always be executed. The *hello* would not be printed because when the parsing fails, it jumps to the catch exception block instead.

### Question 5

- a)
```java
Four states of threads:
- new: a thread has been created but not started
- runnable: a call to the start() method has moved it into the runnable state where it is waiting to be selected for execution
- running: the thread is the currently running thread
- blocked: the thread cannot execute due to slee() or I/O wait
```
- b)
```java
public void go(){
  try{
    Thread.sleep(3000);
  }
  catch(InterruptedException e){
    e.printStackTrace();
  }
  doMore();
}
```
- c) If a method is synchronised then a thread has to get the key for the method, before it can enter it. If the key is not available it will wait until it is. Once a thread has finished executing a synchronised method, it relinquishes the key for the next thread.
- d) A deadlock will happen when there are method A and method B with Thread 1 getting a key to method A and Thread 2 getting a key to method B, and Thread 1 would like to access method B and Thread 2 would like to access method A. This will cause them to wait forever. It is a serious problem for Java programmers as JVM will not know that deadlock has occurred, and has no mechanism for handling thread deadlock.
- e) While the methods that it calls have been synchronised and cannot be interrupted, the AirlockExitSequence() method could be interrupted between method calls and it is something undesirable.

### Question 6

- a) If a class is serialisable, then objects of the class can be automatically saved to a file.
- b) by implementing Serializable
- c) During serialization, a transient variable wold not be saved. DUring deserialization, a transient variable will assume the default/null value when its containing object is deserialised.
- d) (i)
```java
1. output to a file named "MyObj.ser"
2. To create the ability to write a save(serialised) object and chain that stream to the FileOutputStream so that it can be written to a file.
3. Serialises the String object referenced by a and writes it to the file.
4. This closes the ObjectOutputStream and the file.
```
- d) (ii) hello
- e) It is trying to read the response given by the server char by char and then print it out char by char.
- f) Because port 0 and 1023 inclusive are reserved for well known services, such as Telnet and FTP.
