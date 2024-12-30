**Panel:** A Panel is a container that is used to hold and organize other components such as buttons, labels, text fields, etc.

**Button:** A Button is a GUI component that can be clicked by the user to perform a certain action.

**Canvas:** A Canvas is a component that allows drawing and rendering graphics in a custom area.

**Label:** A Label is a GUI component that displays a text message or an icon.

**TextField:** A TextField is a GUI component that allows the user to enter or edit a single line of text.

**Pack:** The pack() method is used to resize a window to fit its contents.

**List:** A List is a GUI component that displays a list of items, where the user can select one or multiple items.

**Window:** A Window is a container that represents a top-level window, such as a JFrame or JDialog.

**setBounds:** The setBounds() method is used to set the position and size of a component.

**TextArea:** A TextArea is a GUI component that allows the user to enter or edit multiple lines of text.

**Container:** A Container is a component that can hold and organize other components.

**ComboBox:** A ComboBox is a GUI component that combines a drop-down list with an editable text field, allowing the user to select an item from the list or enter a custom value.

**Checkbox:** A Checkbox is a GUI component that represents a boolean value, which can be either checked or unchecked.

**Frame:** A Frame is a top-level window that can be resized, minimized, maximized, and closed.

**PasswordField:** A PasswordField is a GUI component that allows the user to enter a masked password.



-   **EXIT_ON_CLOSE:** A constant that specifies that the program should exit when the user closes the window. This is typically used with the `setDefaultCloseOperation()` method of JFrame.
    
-   **DISPOSE_ON_CLOSE:** A constant that specifies that the window should be disposed of (removed from the screen) when the user closes it. This is typically used with the `setDefaultCloseOperation()` method of JDialog.
    
-   **DO_NOTHING_ON_CLOSE:** A constant that specifies that no action should be taken when the user closes the window. This is typically used with the `setDefaultCloseOperation()` method of JFrame or JDialog when you want to handle the window close event yourself.
    
-   **HIDE_ON_CLOSE:** A constant that specifies that the window should be hidden when the user closes it. This is typically used with the `setDefaultCloseOperation()` method of JFrame or JDialog when you want to hide the window instead of closing it.
    
-   **showConfirmDialog():** A method that displays a dialog box with a message and OK/Cancel buttons and returns the user's response. This method is typically used to confirm an action before proceeding.
    
-   **showInputDialog():** A method that displays a dialog box with a message and an input field and returns the user's input. This method is typically used to prompt the user for input.
    
-   **showMessageDialog():** A method that displays a dialog box with a message and an OK button. This method is typically used to display information to the user.
    
-   **showOptionDialog():** A method that displays a dialog box with a message, a list of options, and OK/Cancel buttons and returns the user's response. This method is typically used to present the user with a set of options to choose from.



-   JPasswordField:
| Constructor                                      | Description                                                                                    |
| ------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| `JPasswordField()`                               | Constructs a new `JPasswordField`, with a default document, null starting text string, and 0 column width. |
| `JPasswordField(int columns)`                    | Constructs a new empty `JPasswordField` with the specified number of columns.                   |
| `JPasswordField(String text)`                    | Constructs a new `JPasswordField` initialized with the specified text.                          |
| `JPasswordField(String text, int columns)`       | Construct a new `JPasswordField` initialized with the specified text and number of columns.    |

```java

JPasswordField passwordField = new JPasswordField();
```

```java
  import javax.swing.*;    
  public class PasswordFieldExample {  
      public static void main(String[] args) {    
      JFrame f=new JFrame("Password Field Example");    
       JPasswordField value = new JPasswordField();   
       JLabel l1=new JLabel("Password:");    
          l1.setBounds(20,100, 80,30);    
           value.setBounds(100,100,100,30);    
              f.add(value);  f.add(l1);  
              f.setSize(300,300);    
              f.setLayout(null);    
              f.setVisible(true);     
  }  
  }
```


- JTextArea:
| Constructor                                  | Description                                                                                            |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------ |
| `JTextArea()`                                | Creates a text area that displays no text initially.                                                  |
| `JTextArea(String s)`                         | Creates a text area that displays specified text initially.                                           |
| `JTextArea(int row, int column)`              | Creates a text area with the specified number of rows and columns that displays no text initially.    |
| `JTextArea(String s, int row, int column)`    | Creates a text area with the specified number of rows and columns that displays specified text.     |

```java
JTextArea textArea = new JTextArea();
```

```java
1.  import javax.swing.*;  
2.  public class TextAreaExample  
3.  {  
4.       TextAreaExample(){  
5.          JFrame f= new JFrame();  
6.          JTextArea area=new JTextArea("Welcome to javatpoint");  
7.          area.setBounds(10,30, 200,200);  
8.          f.add(area);  
9.          f.setSize(300,300);  
10.          f.setLayout(null);  
11.          f.setVisible(true);  
12.       }  
13.  public static void main(String args[])  
14.      {  
15.     new TextAreaExample();  
16.      }}
```



-   JLabel:
| Constructor                                    | Description                                                                                                   |
| ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `JLabel()`                                      | Creates a `JLabel` instance with no image and with an empty string for the title.                             |
| `JLabel(String s)`                              | Creates a `JLabel` instance with the specified text.                                                          |
| `JLabel(Icon i)`                                | Creates a `JLabel` instance with the specified image.                                                         |
| `JLabel(String s, Icon i, int horizontalAlignment)` | Creates a `JLabel` instance with the specified text, image, and horizontal alignment.                        |

```java
JLabel label = new JLabel("My Label");
```

```java
1.  import javax.swing.*;  
2.  class LabelExample  
3.  {  
4.  public static void main(String args[])  
5.      {  
6.      JFrame f= new JFrame("Label Example");  
7.      JLabel l1,l2;  
8.      l1=new JLabel("First Label.");  
9.      l1.setBounds(50,50, 100,30);  
10.      l2=new JLabel("Second Label.");  
11.      l2.setBounds(50,100, 100,30);  
12.      f.add(l1); f.add(l2);  
13.      f.setSize(300,300);  
14.      f.setLayout(null);  
15.      f.setVisible(true);  
16.      }  
17.      }
```


-   JTextField:
| Constructor                       | Description                                                           |
|-----------------------------------|-----------------------------------------------------------------------|
| `JTextField()`                    | Creates a new TextField                                               |
| `JTextField(String text)`         | Creates a new TextField initialized with the specified text.         |
| `JTextField(String text, int columns)`| Creates a new TextField initialized with the specified text and columns. |
| `JTextField(int columns)`         | Creates a new empty TextField with the specified number of columns.  |

```java
JTextField textField = new JTextField();
```

```java
1.  import javax.swing.*;  
2.  class TextFieldExample  
3.  {  
4.  public static void main(String args[])  
5.      {  
6.      JFrame f= new JFrame("TextField Example");  
7.      JTextField t1,t2;  
8.      t1=new JTextField("Welcome to Javatpoint.");  
9.      t1.setBounds(50,100, 200,30);  
10.      t2=new JTextField("AWT Tutorial");  
11.      t2.setBounds(50,150, 200,30);  
12.      f.add(t1); f.add(t2);  
13.      f.setSize(400,400);  
14.      f.setLayout(null);  
15.      f.setVisible(true);  
16.      }  
17.      }
```

-   JFrame:
| Constructor                                    | Description                                                                                                                     |
|------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| JFrame()                                       | It constructs a new frame that is initially invisible.                                                                         |
| JFrame(GraphicsConfiguration gc)               | It creates a Frame in the specified GraphicsConfiguration of a screen device and a blank title.                                |
| JFrame(String title)                           | It creates a new, initially invisible Frame with the specified title.                                                          |
| JFrame(String title, GraphicsConfiguration gc) | It creates a JFrame with the specified title and the specified GraphicsConfiguration of a screen device.                        |

```java
JFrame frame = new JFrame("My Frame");
```

```java
1.  import java.awt.FlowLayout;  
2.  import javax.swing.JButton;  
3.  import javax.swing.JFrame;  
4.  import javax.swing.JLabel;  
5.  import javax.swing.JPanel;  
6.  public class JFrameExample {  
7.      public static void main(String s[]) {  
8.          JFrame frame = new JFrame("JFrame Example");  
9.          JPanel panel = new JPanel();  
10.          panel.setLayout(new FlowLayout());  
11.          JLabel label = new JLabel("JFrame By Example");  
12.          JButton button = new JButton();  
13.          button.setText("Button");  
14.          panel.add(label);  
15.          panel.add(button);  
16.          frame.add(panel);  
17.          frame.setSize(200, 300);  
18.          frame.setLocationRelativeTo(null);  
19.          frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);  
20.          frame.setVisible(true);  
21.      }  
22.  }
```


-   JPanel:
| Constructor                                      | Description                                                                                                    |
|--------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| JPanel()                                         | It is used to create a new JPanel with a double buffer and a flow layout.                                       |
| JPanel(boolean isDoubleBuffered)                 | It is used to create a new JPanel with FlowLayout and the specified buffering strategy.                        |
| JPanel(LayoutManager layout)                     | It is used to create a new JPanel with the specified layout manager.                                           |

```java
JPanel panel = new JPanel();
```

```java
1.  import java.awt.*;  
2.  import javax.swing.*;  
3.  public class PanelExample {  
4.       PanelExample()  
5.          {  
6.          JFrame f= new JFrame("Panel Example");    
7.          JPanel panel=new JPanel();  
8.          panel.setBounds(40,80,200,200);    
9.          panel.setBackground(Color.gray);  
10.          JButton b1=new JButton("Button 1");     
11.          b1.setBounds(50,100,80,30);    
12.          b1.setBackground(Color.yellow);   
13.          JButton b2=new JButton("Button 2");   
14.          b2.setBounds(100,100,80,30);    
15.          b2.setBackground(Color.green);   
16.          panel.add(b1); panel.add(b2);  
17.          f.add(panel);  
18.                  f.setSize(400,400);    
19.                  f.setLayout(null);    
20.                  f.setVisible(true);    
21.          }  
22.          public static void main(String args[])  
23.          {  
24.          new PanelExample();  
25.          }  
26.      }
```

-   JButton:
| Constructor                  | Description                                        |
|------------------------------|----------------------------------------------------|
| JButton()                    | It creates a button with no text and icon.          |
| JButton(String s)            | It creates a button with the specified text.       |
| JButton(Icon i)              | It creates a button with the specified icon object.|

```java
JButton button = new JButton("My Button");
```

```java
1.  import javax.swing.*;    
2.  public class ButtonExample {  
3.  public static void main(String[] args) {  
4.      JFrame f=new JFrame("Button Example");  
5.      JButton b=new JButton("Click Here");  
6.      b.setBounds(50,100,95,30);  
7.      f.add(b);  
8.      f.setSize(400,400);  
9.      f.setLayout(null);  
10.      f.setVisible(true);   
11.  }  
12.  }
```


-   main:
```java
public static void main(String[] args) {     // Your code here }
```



-   canvas:

```java
Canvas canvas = new Canvas();
```


-   setColor:
```java
graphics.setColor(Color.RED);
```



-   drawOval:
```java
graphics.drawOval(x, y, width, height);
```


-   true:
```java
boolean myBoolean = true;
```



-   drawString:
```java
graphics.drawString("My Text", x, y);
```



-   false:
```java
boolean myBoolean = false;
```



-   setFont:
```java
graphics.setFont(new Font("Serif", Font.PLAIN, 12));
```



