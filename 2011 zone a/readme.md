# Zone A 2011 Answers

### Question 1

- a) (i) size, name
- a) (ii)
```java
Dog size is 0
Dog name is null
```
- a) (iii)
```java
public PoorDogB(int size, String name){
  this.size = size;
  this.name = name;
}
```
- a) (iv) Line 18. This is because the constructor used is no longer the default constructor with no input parameters but the new constructor that requires 2 inputs.
- b) Unlimited.
- c) (i) It is to invoke the constructor from the parent class.
- c) (ii) 25, 46, 51
- c) (iii)
```java
line 25: 'super' keyword must be first, not 'this'
line 46: the constructor has already existed
line 51: the superClass does not have constructor of (String, String) input
```

### Question 2

- a) (ii) No, there is no unreachable object.
- a) (iii) (A) Will not cause an object to be unreachable since g5 is still pointing to the object pointed by g1.
- a) (iii) (B) g1 will still be pointing to the object referenced by g5. So there still will not be nay unreachable objects.
- a) (iii) (C) Still will not affect, since g4 will still be using the object even if g3 is no longer using the object.
- a) (iii) (D) This will cause an unreachable object because the object created is only used by g2 and nobody else.
- b) (i) Parameterising here means that ArrayList could take in any type of objects. However, the compiler can only take or accept a certain type. So parameterising is to make ArrayList to accept object of a certain type so that the compiler can compile.
- b) (ii) The syntax to parameterize array lists: the type is placed in between the angle brackets after ArrayList.
- b) (iii)
```java
Goodbye not found
Drood
```

### Question 3

- a)
```java
JButton button = new JButton ("Question 3");
button.addActionListener(new ActionListener(){
  public void actionPerformed(ActionEvent e){
    JLabel label = new JLabel("You clicked me!");
  }
});
```
- b) (i) True
- b) (ii) No
- c)
```java
public class C extends H implements G{
  public void hello(int n){
    int i=0;
    while(i<n){
      System.out.println("hello");
      i++;
    }
  }
  public void goodbye(int n){
    if(n < 0){
      System.out.println("goodbye");
    }
  }
}
```
- d) (i)
```java
import java.awt.*;
public abstract class SpaceObject{
  private int xPos, yPos;
  private xMove, yMove;
  public SpaceObject(int x, int y){
    xPos = x;
    yPos = y;
  }
  public void move(){
    xMove = (int)Math.random()*10;
    yMove = (int)Math.random()*10;
    xPos += xMove;
    yPos += yMove;
  }
  public int getxPos(){
    return xPos;
  }
  public int getyPos(){
    return yPos;
  }
  public abstract void draw(Graphics g);
}
```
- d) (ii)
```java
import java.awt.*;
public class Comet2 extends SpaceObject{
  public comet2(int x, int y){
    super(x,y);
  }
  public void draw(Graphics g){
    g.setColor(Color.ORANGE);
    g.fillOval(getxPost(), getyPos(), 50, 75);
  }
}
```

### Question 4

- a)
```java
import java.awt.*;
import java.awt.evet.*;
import javax.swing.*;
public class ColourCircle{
  JFrame frame;
  JPanel panel;
  JButton button;
  public static void main(String[]args){
    ColourCircle cc = new ColourCircle();
    cc.go();
  }
  public void go(){
    frame = new JFrame("Question four");
    panel = new JPanel();
    button = new JButton("Blue circle above");
    frame.add(panel, BorderLayout.CENTER);
    frame.add(button, BorderLayout.SOUTH);
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setSize(400,400);
    frame.setVisible(true);
  }
  public class NewDrawPanel extends JPanel{
    public void paintComponent(Graphics g){
      Graphics2D g2 = (Graphics2D) g;
      g2.setColor(Color.BLUE);
      g2.fillOval(125,125,150,150);
    }
  }
}
```
- b) Let's finish

### Question 5

- a) (i) The class would display the source code of the webpage given, http://www.gold.ac.uk, and the source code would be displayed exactly as formatted.
- a) (ii) It will give IOException.
- b) (i) This is due to the scheduling that happens in the OS. Since this cannot be determined by programmer, it totally depends on the OS. Thus it can vary.
- b) (ii)
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
- c) Deadlock happens when there are 2 threads holding on to the keys of the methods that later each of them want to access. This will cause forever waiting, leading to deadlock.
- d) This is because this cannot be handled by the JVM as it does not have the mechanism to do so. Also, it might not even know if it happens.

### Question 6

- a) A
- b) True
- c) Default value / null
- d) (i) The class would serialize/save an object of type String and one of type Q6d to a file called "MyObj.ser"
- d) (ii)
```java
try{
  FileInputStream fis = new FileInputStream("MyObj.ser");
  ObjectInputStream ois = new ObjectInputStream(fis);
  a = (String) ois.readObject();
  b = (String) ois.readObject();
}
catch(Exception e){
  e.printStackTrace();
}
```
- e) (i) 190.165.1.103
- e) (ii) 4242
- e) (iii) It would be printed to the screen
- f) because 0 to 1023 inclusive is reserved for well known services like Telenet and FTP.
