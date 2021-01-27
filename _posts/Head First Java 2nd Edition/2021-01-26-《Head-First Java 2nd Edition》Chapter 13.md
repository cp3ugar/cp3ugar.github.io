---
layout: post
title: "《Head First Java 2nd Edition》Chapter 13"
date: 2021-01-26
excerpt: "Work on Your Swing"
tags: [reading notes,Head First Java,Java]
comments: true
---

# Swing components

### A widget is technically a Swing <u>Component</u>. Almost every thing you can stick in a GUI extends from javax.swing.JComponent.

# The Big Three layout managers: border,flow,and box

### BorderLayout

A BorderLayout manager divides a background component into five regions. You can add only one component into five regions. You can add only one component per region to a background controlled by a BorderLayout manager. Components laid out by this manager usually don't get to have their preferred size. **BorderLayout is the default layout manager for a frame!**

![image-20210127144458182](F:\Nicholas\MyProject\cp3ugar.github.io\assets\img\image-20210127144458182.png)

### FlowLayout

A FlowLayout manager acts kinds of like a word processor,except with components instead of words. Each component is the size it wants to be,and they're laid out left to right in the order that they're added,with "word-wrap" turned on. So when a component won;t fit horizontally,it drops to the next "line" in the layout. **FlowLayout is the default layout manager for a panel!**

![image-20210127144707249](F:\Nicholas\MyProject\cp3ugar.github.io\assets\img\image-20210127144707249.png)

### BoxLayout

A BoxLayout manager is like FlowLayout in that each component gets to have its own size,and the components are placed in the order in which they're added. But,unlike FlowLayout,a BoxLayout manager can stack the components vertically. It's like a FlowLayout but instead of having automatic 'component wrapping',you can insert a sort of 'component return key' and **<u>force</u>** the components to start a new line.

![image-20210127144953518](F:\Nicholas\MyProject\cp3ugar.github.io\assets\img\image-20210127144953518.png)

