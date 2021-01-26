---
layout: post
title: "《Head First Java 2nd Edition》Chapter 12"
date: 2021-01-25
excerpt: "A Very Graphic Story"
tags: [reading notes,Head First Java,Java]
comments: true
---

# BULLET POINTS

- To make a GUI,start with a window,usually a JFrame

  `JFrame frame = new JFrame();`

- You can add widgets (buttons,text fields,etc.) to the JFrame using

  `frame.getContentPane().add(button);`

- Unlike most other components,the JFrame doesn't let you add to it directly,so you must add to the JFrame's content pane

- To make the window display,you must give it a size and tell it be visible

  `frame.setSize(300, 300);`

  `frame.setVisible(true);`

- To know when the user clicks a button you need to listen for a GUI event

- To listen for an event,you must register your interest with an event source. An event source is the thing that 'fires' an event based on user interaction

- The listener interface gives the event source a way to call you back,because the interface defines the method(s) the event source will call when an event happens

- To register for events with a source,call the source's registration method. Registration methods always take the form of: **add<EventType>Listener**. To register for a button's ActionEvents,for example,call:

  `button.addActionListener(this);`

- Implement the listener interface by implementing all of the interface's event-handing methods. Put your event-handing code in the listener call-back method. For ActionEvents,the method is:

  ```java
  public void actionPerformed(ActionEvent event){
  	button.setText("you clicked!");
  }
  ```

- The event object passed into the event-handler method carries information about the event,including the source of the event

- You can draw 2D graphics directly on to a widget

- You can draw your own graphics,make a subclass of JPanel and override the paintComponent() method

- The paintComponent() method is called by the GUI system. YOU NEVER CALL IT YOURSELF. The argument to paintComponent() is a Graphics object that gives you a surface to draw on,which will end up on the screen. You cannot construct that object yourself

- Typical methods to call on a Graphics object are:

  `graphics.setColor(Color.blue);`

  `g.fillRect(20, 50, 100, 120);`

- To draw a .jpg,construct an Image using:

  `Image image = new ImageIcon("catzilla.jpg").getImage();`

  and draw the imagine using:

  `g.drawImage(image, 3, 4, this);`

- The object referenced by the Graphics parameter to paintComponent() is actually an instance of the Graphics2D class. The Graphics 2D class has a variety of methods including:

  fill3DRect(),draw3DRect(),rotate(),scale(),shear(),transform()

- To invoke the Graphics2D methods,you must cast the parameter from a Graphics object to a Graphics2D object:

  `Graphics2D g2d = (Graphics2D)g;`

# Inner class

You can have one class nested inside another. It's easy. Just make sure that the definition for the inner class is inside the curly braces of the outer class.

### An inner class can use all the methods and variables of the outer class,even the private ones. The inner class gets to use those variables and methods just as if the methods and variables were declared within the inner class.

![image-20210126103248536](F:\Nicholas\MyProject\cp3ugar.github.io\assets\img\image-20210126103248536.png)

# An <u>inner</u> class instance must be tied to an <u>outer</u> class instance

An **inner** object must be tied to a specific **outer** object on the heap.

![image-20210126103652326](F:\Nicholas\MyProject\cp3ugar.github.io\assets\img\image-20210126103652326.png)

![image-20210126103659233](F:\Nicholas\MyProject\cp3ugar.github.io\assets\img\image-20210126103659233.png)

![image-20210126103709250](F:\Nicholas\MyProject\cp3ugar.github.io\assets\img\image-20210126103709250.png)

