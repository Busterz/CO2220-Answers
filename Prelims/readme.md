# Prelims 2017 Answers

### Question 1

- a) (i) There is no bark() method in Animal class. Can change to: *Dog b = new Dog()* or *((Dog)b).bark()*.
- a) (ii)
```java
Animals can move
Dogs can walk and run
Dogs can bark
```
- b)
```java
A
B
B
B
B
```
- c) (i) The functionality: to calculate m^n.
- c) (ii) foo(2,8): 256. foo(3,5): 243.
- c) (iii) Line A and Line B will each call foo(...) 4 times.
- d) (i) [stack and heap diagram here]
- d) (ii) No, there is no any unreachable objects.

### Question 2

- a) (i) Correct
- a) (ii) Correct
- a) (iii) Correct
- a) (iv) Not correct
- b) (i)
```java
interface GraphicsObject{
  int getArea();
  void draw();
}
```
- b) (ii)
```java
public class Rectangle implements GraphicsObject{
  private int length, width;
  public Rectangle (int l, int w){
    length = l;
    width = w;
  }
}
```
- b) (iii)
```java
int getArea(){
  return length * width;
}
void draw(){
}
```
- c) Call explicitly the constructor:
```java
public Y(){
  super(2);
  System.out.println(2);
}
```
- d)
```java
One
Two
Three
```
- e) ii
- f) (i) Valid
- f) (ii) Valid
- f) (iii) Valid
- f) (iv) Not valid

### Question 3

- a) (i) It draws up a window of size 500x500 with a blank panel.
- a) (ii)
```java
public class MyDrawPanel extends JPanel{
  public void paintComponent(Graphics g){
    Graphics2D g2 = (Graphics2D) g;
    g2.setColor(Color.BLUE);
    g2.fillRect(0,0,80,80);
  }
}
```
- a) (iii)
```java
public class MyDrawPanel extends JPanel{
  public void paintComponent(Graphics g){
    Graphics2D g2 = (Graphics2D) g;
    g2.setColor(Color.BLUE);
    g2.fillRect(x,0,80,80);
    x++;
    frame.repaint();
  }
}
```
- a) (iv)
```java
frame.getContentPane().add(drawPanel, BorderLayout.CENTER);
```
- a) (v)
```java
JButton button = new JButton("Question 3");
frame.getContentPane().add(button, BorderLayout.SOUTH);
```
- b)
+-----------+
|     C     |
+-----+-----+
|  D  |  B  |
+-----+-----+

### Question 4

- a) i
- b) 123BD
- c)
```java
YourException
MyException
```
- d) (i)
```java
public String readLineAt(File f, int lineNumber){
  if(lineNumber < 0){
    return null;
  }
  String line = null;
  int i = 0;
  Scanner sc = new Scanner (new FileReader(f));
  while(sc.hasNextLine()){
    line = s.nextLine();
    if(i == lineNumber){
      break;
    }
    else{
      i++;
    }
  }
  sc.close();
  return line;
}
```
- d) (ii)
```java
public File mergeFiles(File f1, File f2){
  File out = new File("output.txt");
  FileWriter fw = new FileWriter(out);
  int i=0;
  String line;
  while((line = readLineAt(f1, i)) != null){
    fw.write(line + "\n");
    String line2 = readLineAt(f2, i);
    if(line2 != null){
      fw.write(line2 + "\n");
    }
    i++;
  }
  fw.close();
  return out;
}
```

### Question 5

- a) iv
- b) iii
- c) Transient marks a member variable not to be serialized when it is persisted to streams of bytes. When an object is transferred through the network, the object needs to be serialized. Serialization converts the object state to serial bytes. Those bytes are sent over the network and the object is recreated from those bytes. Member variables marked by the java transient keyword are not transferred, they are lost intentionally.
- d) (i)
```java
Socket socket = serverSocket.accept();
PrintWriter writer = new PrintWriter(socket.getOutputStream());
writer.println("Bye bye now!");
writer.close();
```
- d) (ii) 3

### Question 6

- a) (i) F
- a) (ii) T
- a) (iii) F
- b) myMethod1() cannot be overridden since it is final.
- c) Two threads, sharing the same resource with locks.
- d) (i) It is due to the scheduling system of the Operating System. It cannot be determined explicitly. It all depends on the Operating System itself, thus the inconsistency.
- d) (ii) Change the run method by adding a synchronized block, so that they do not use *pd* at the same time:
```java
public void run(){
  synchronized(pd){
    pd.printCount();
  }
}
```
- d) (iii)
```java
Starting Thread1
Starting Thread2
Counter = 0
Counter = 1
Counter = 2
Counter = 3
Counter = 4
Counter = 0
Counter = 1
Counter = 2
Counter = 3
Counter = 4
```
