# Zone A 2016 Answers

### Question 1

- a) 11
- b) A
- c) (i) The class Laurel will complile.
- c) (ii) The constructor for Hardy requires an input argument, thus the compilation error.
- d) (i) It is invoking the other constructor of Jack with input of String type and pass the String input which in this case is to store the location in String type.
- d) (ii)
```java
public Jill(String location, String thing){
  super(location);
  this.thing = thing;
}
```
- e) There is an error in the condition checking part of the 'for' loop. The value of *i* will keep being decremented. So, when *i = 0* -> *i >= 0 && a[0] != find* will still return true (assuming that the element found is not the desired one) and the body code will execute. Then, after *i--*, *i = -1* and this will cause *i >= 0* to return false. However, the condition reading does not stop there and have to check *a[0] != find*. However, there is no *a[-1]*, thus this will produce ArrayOutOfBoundsException.

### Question 2

- a) The class Dog is an abstract class and thus it cannot be instantiated.
- b) A
- c) (i)
```java
public class Cat implements Animal{
  public int numberOfFeet(){
    return 4;
  }
}
```
- c) (ii)
```java
public class PetCat extends Cat{
  private String name;
  public PetCat(String name){
    this.name = name;
  }
  public String getName(){
    return name;
  }
}
```
- d) ht[1] = ht[4]. Statement 2.
- e) (i) speak() method
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
- a) (E) T
- b)
```java
class button2Listener implements ActionListener{
  public void actionPerformed(ActionEvent e){
    button1.setText("Click me now!");
    frame.repaint();
  }
}
class button1Listener implements ActionListener{
  public void actionPerformed(AcionEvent e){
    button2.setText("Don't click him again!");
    frame.repaint();
  }
}
```

### Question 4

- a) (A) F
- a) (B) F
- a) (C) T
- b) (i) It is to prevent the class from being instantiated. This means that there should not be any objects created from this class. This might mean that the class is a utility class (only contains static member).
- b) (ii) B
- b) (iii) A
- b) (iv)
```java
public static ArrayList<SL> fromSerialized(String filename){
  ArrayList<SL> sl = null;
  ObjectInputStream ois;
  try{
    ois = new ObjectInputStream (new FileInputStream(filename));
    sl = (ArrayList<SL>) ois.readObject():
    ois.close();
  }
  catch(FileNotFoundException e){
    System.err.format("File not found! %s", e);
    return sl;
  }
  catch(Exception e){
    System.err.format("File not found! %s", e);
    return sl;
  }
  return sl;
}
```
- c)
```java
ShowFile3 -> infinite loop
ShowFile2 -> run correctly
ShowFile4 -> will throw FileNotFoundException
```

### Question 5

- a) (i) There will be compilation error on how the final variable is not initialised.
- a) (ii) It is Java conventional way to say that it is a constant.
- b) It will give compilation error on how the method *askToPance* cannot be overridden.
- c) Compilation error on how the variable area is final and cannot be assigned.
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

- a) C
- b) B
- c) (i) Server machine at 190.165.1.103
- c) (ii) It will print out the sentences received
- d) A
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
