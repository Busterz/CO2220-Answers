# Zone B 2016 Answers

### Question 1

- a) 5
- b) A
- c) (i) Ant.
- c) (ii) Because Dec needs input argument
- d) (i) It is to call the superclass constructor
- d) (ii)
```java
public Jack(){
  this("down the hill");
}
```
- e) There is an error in the condition checking part of the 'for' loop. The value of *i* will keep being decremented. So, when *i = 0* -> *i >= 0 && a[0] != find* will still return true (assuming that the element found is not the desired one) and the body code will execute. Then, after *i--*, *i = -1* and this will cause *i >= 0* to return false. However, the condition reading does not stop there and have to check *a[0] != find*. However, there is no *a[-1]*, thus this will produce ArrayOutOfBoundsException.

### Question 2

- a) Abstract cannot be instantiated.
- b) B
- c) (i)
```java
public class Dog implements Animal{
  public boolean isCarnivore(){
    return true;
  }
}
```
- c) (ii)
```java
public class PetDog extends Dog{
  private int age;
  public PetDog(int age){
    this.age = age;
  }
  public int getAge(){
    return age;
  }
}
```
- d) Statement 2.
- e) (i) Machine constructor
- e) (ii)
```java
The machines are rising
I am your robot overlord
The robot uprising has begun
```

### Question 3

- a) (A) T
- a) (B) T
- a) (C) F
- a) (D) T
- a) (E) F
- b)
```java
public void go(){
  frame = new JFrame();
  button1 = new JButton ("Click me");
  button1.addActionListener(new ActionListener{
    public void actionPerformed(AcionEvent e){
      button2.setText("Don't click him again!");
      frame.repaint();
    }
  });
  button2 = new JButton ("Don't click him, click me!");
  button2.addActionListener(new ActionListener{
    public void actionPerformed(ActionEvent e){
      button1.setText("Click me now!");
      frame.repaint();
    }
  });
  frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  frame.getContentPane().add(BorderLayout.EAST, button1);
  frame.getContentPane().add(BorderLayout.WEST, button2);
  frame.setSize(500, 500);
  frame.setVisible(true);
}
```
- c) (i)
```java
class CircleDrawPanel extends JPanel{
  public void paintComponent(Graphics g){
    super.paintComponent(g);
    Graphics2D g2 = (Graphics2D) g;
    g2.setColor(color);
    g2.fillOval(x, y, diameter, diameter);
    x++;
    this.repaint();
  }
}
```
- c) (ii)
```java
class CircleDrawPanel extends JPanel{
  public void paintComponent(Graphics g){
    super.paintComponent(g);
    Graphics2D g2 = (Graphics2D) g;
    g2.setColor(color);
    if(x > getWidth()) x = 0;
    g2.fillOval(x, y, diameter, diameter);
    x++;
    this.repaint();
  }
}
```

### Question 4

- a) (A) F
- a) (B) T
- a) (C) F
- b) (i) It is to prevent the class from being instantiated. This means that there should not be any objects created from this class. This might mean that the class is a utility class (only contains static member).
- b) (ii) C
- b) (iii) A
- b) (iv)
```java
public static void serializeToDisk(ArrayList<SL>teams){
  ObjectOutputStream oos;
  try{
    oos = new ObjectOutputStream(new FileOutputStream("teams.ser"));
    oos.writeObject(teams);
    oos.close();
  }
  catch(FileNotFoundException e){
    System.err.format("File not found! %s", e);
  }
  catch(Exception e){
    System.err.format("Error reading from file: %s", e);
  }
}
```
- c)
```java
ShowFile6 -> infinite loop
ShowFile2 -> run correctly
ShowFile5 -> will not compile
```

### Question 5

- a) (i) There will be compilation error on how the final variable is not initialised.
- a) (ii) It is Java conventional way to say that it is a constant.
- b) Final variable cannot be assigned.
- c) Class cannot be inherited.
- d) (i) C
- d) (ii)
```java
public class AbsVal{
  static int onlyPositive(int x) throws NewException{
    if(x < 0) throw newException(x + "is a negative number, positive numbers only");
    return x;
  }
}
```

### Question 6

- a) idle, starts, run/execute
- b) A
- c) (i) Server machine at 190.165.1.103
- c) (ii) 4242
- d) B
- e) (A) T
- e) (B) F
- e) (C) T
- e) (D) F
- f) continuously showing either *hello* or *goodbye* or both also possible.
```java
goodbye   or    hello
hello     or    goodbye
.
.
.
```
