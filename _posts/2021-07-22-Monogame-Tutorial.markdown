---
title: Monogame Tutorial
subtitle: Monogame Tutorial
layout: post_detail
date-created: 2021-07-22
date-edited: 2021-07-23
img: dreams.png
thumbnail: 2021-07-22-Monogame-Tutorial-thumbnail.png
alt: image-alt
category: [Post, Study]
description: Monogame Tutorial
comments: true
---

# Monogame Tutorial
### 2021-07-22
1.	Introduction
2.	Installing visual Studio and Monogame
3.	Creating new projects and code organization
    1.	Windows CrossPlatform 
    2.	Constructor: public game1()
    * We can change windows size or basic settings
    ![Constructor Game1](/img/{{ page.url }}/constructor-game-1.png){: .img-responsive}
    3.	Initialize method
    * When game starts it is executed, setting
    ![Initialize Method](/img/{{ page.url }}/initialize-method.png){: .img-responsive}
    4.	LoadContent method
    * Load Assets like graphics
    ![LoadContent Method](/img/{{ page.url }}/load-content-method.png){: .img-responsive}
    5.	Update method
    * Gameloop => 60times in a second
    * Game frame
    ![Update Method](/img/{{ page.url }}/update-method.png){: .img-responsive}
    6.	Draw method
    * E.g. show target
    * Runs in every frame
    ![Draw Method](/img/{{ page.url }}/draw-method.png){: .img-responsive}

4.	Importing assets with the Pipeline tool
    1. Content Pipeline: The MonoGame Pipeline Tool is used to create and manage MonoGame content projects. The files in content projects are processed by the MonoGame Pipeline tool and outputted as . xnb files for use in CocosSharp and MonoGame applications.
    ![Monogame Content Builder](/img/{{ page.url }}/monogame-content-builder.png){: .img-responsive}
    * Add Existing Item - Build
    * .xnb files

5.	Drawing graphics #1
    1. Sprites: you take your individual animation frames (of characters, objects, etc.), and drag and drop them into TexturePacker. Then TexturePacker combines them into sprite sheets, which you can then load into your game.
    2. Load Content
    * Term – SpriteBatch: A SpriteBatch is used to draw a whole bunch of sprites all at one time. ... We will then draw our sprites, and when we're done, we will indicate that we are done drawing our batch of sprites. Go down to the Draw() method and add the following three lines of code:

    ```C#
    // Assign Imported assets(.xnb files = stream target) to targetSprite
    targetSprite = Content.Load<Texture2D>("target");
    ```

6.	Drawing graphics #2
    1. _spriteBatch.Draw(targetSprite, new Vector2(0,0), Color.White);
    * Three parameters
    * Vector: position (Origin: (0, 0)), unit pixel, increase y  downer
    * Color: tint
    2.	Drawing Order

7.	Printing Text(SpriteFonts): Blue print of fonts in Monogame
    1.	SolutionExploer – Content – GalleryFont.sprite
    * In draw method:

    ```C#
    _spriteBatch.DrawString(gameFont, "Test Message", new Vector2(100, 100), Color.White);
    ```

### 2021-07-23
8.	Variables
    1.	Declare variable
    * Vector2 targetPosition = new Vector2(300, 300);
    2.	Using variable
    * _spriteBatch.Draw(targetSprite, targetPosition, Color.White);
    3.	Declare constant variable
    * Doesn’t change and cannot be changed
    * Using const keyword

9.	Mouse Input
    1. State: What mouse do particular moment(click, moving, etc…)
    * Because update method is executed in every frame, score increases more than 1.
    2. Use mRelased that indicates mouse button released state

10.	Shooting the Target
    1. How can we tell that the mouse clicks the target?
    * Calculate the distance between the mouse click point and center of the target
    * If the distance is less than target’s radius, it’s hit
    * The origin point of sprite is upper left corner
    * Offset 
    ```C#
    _spriteBatch.Draw(targetSprite, new Vector2(targetPosition.X - targetRadius, targetPosition.Y - targetRadius), Color.White);
    ```

11.	Randomness
    1. Change Target Location Randomly after hit
    * // Change target Position randomly
    * // Range is exclusive
    * Random random = new Random();
    ```C#
    targetPosition.X = random.Next(0, _graphics.PreferredBackBufferWidth);
    targetPosition.Y = random.Next(0, _graphics.PreferredBackBufferHeight);
    ```


---

### Reference
[[2021 Update!] Make Games with MonoGame - Installation and Development Fundamentals - Kyle Schaub](https://www.youtube.com/watch?v=sPH-sNTSrhw&t=0s){:target="_blank"}