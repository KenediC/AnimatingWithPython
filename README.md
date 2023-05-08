# AnimatingWithPython

This project was a simple test to see if I could apply some of the knowledge I had learned the past few weeks to a more finished work. It depicts a day/night cycle of a mountain range. All in all, it’s very simple, but it taught me a lot about mixing computer science with digital art.
  
  This project was useful because it taught me the fundamentals of animating within a coding environment, which was something I was (and still am) inexperienced with. But this animation helped me to see that it is not only possible, but also fairly doable for someone like me who is new to programming. I was able to combine my love of art with something I wanted to learn how to do, which helped me to increase my interest in improving my coding abilities.

The code is as follows:

import simplegui

import random

global xRan 

width = 600

height = 600

r = 50
g = 58
b = 92
global x
x = -50

global p
p = 1
def draw_handler(canvas):
    #background
    global r
    global g 
    global b
    global p
    global color
    if p == 1:
        if r >= 76:
            color = "false"
      
        
        if r <= 50:
            color = "true"
            
        if color == "true":
          r = r + 1
          g = g + 1
          b = b + 2
        
        if color == "false":
          r = r - 1
          g = g - 1
          b = b - 2
      
    backg = "RGB( " + str(r) + "," + str(g) +  "," + str(b) +  ")"
    frame.set_canvas_background(backg)
    p = p + 1
    if p == 10:
        p = 1
    
    #snow layer 1
    for i in range(0,1):
        xRan = random.randint(0, width)
        yRan = random.randint(0, height)
        canvas.draw_circle((xRan, yRan), 2, 1, "#9b9c9e", "#9b9c9e")    
    
    #layer 1
    canvas.draw_polygon([(0, 300), (100, 200), (200, 300)], 2, "#5b5e5c", "#5b5e5c")
    canvas.draw_polygon([(0, 300), (100, 200), (200, 300)], 2, "white", "white")
    canvas.draw_polygon([(0, 300), (200, 300), (200, 600), (0, 600)], 2, "#5b5e5c", "#5b5e5c")
    canvas.draw_polygon([(100, 300), (200, 150), (300, 300)], 2,"#5b5e5c", "#5b5e5c")
    canvas.draw_polygon([(100, 300), (300, 300), (300, 600), (100, 600)], 2,"#5b5e5c", "#5b5e5c")
    canvas.draw_polygon([(300, 350), (500, 250), (600, 350)], 2,"#5b5e5c", "#5b5e5c")
    canvas.draw_polygon([(600, 350), (300, 350), (300, 600), (600, 600)], 2,"#5b5e5c", "#5b5e5c")
    
    #Layer 2
    canvas.draw_polygon([(0, 300), (150, 400), (100, 600), (0, 600)], 2, "#3b3d3c", "#3b3d3c")
    canvas.draw_polygon([(100, 600), (300, 300), (500, 600)], 2, "#3b3d3c", "#3b3d3c")
    canvas.draw_polygon([(350, 455), (500, 300), (600, 400)], 2, "#3b3d3c", "#3b3d3c")
    canvas.draw_polygon([(402, 400), (600, 400), (600, 600), (400, 600)], 2, "#3b3d3c", "#3b3d3c")
    canvas.draw_polygon([(402, 400), (500, 300), (600, 400)], 2, "white", "white")
    
    #layer 3
    canvas.draw_polygon([(0, 600), (150, 350), (300, 600)], 2, "#30302f", "#30302f")
    canvas.draw_polygon([(300, 600), (400, 500), (500, 550),(600, 600)], 2, "30302f", "#30302f")
    canvas.draw_polygon([(550, 600), (600, 530), (600, 600)], 2, "30302f", "#30302f" )
    canvas.draw_polygon([(180, 400), (150, 350), (120, 400)], 2, "white", "white")
    
    #snow layer 2
    for i in range(0,4):
        xRan = random.randint(0, width)
        yRan = random.randint(0, height)
        canvas.draw_circle((xRan, yRan), 2, 1, "#afb0b3", "#afb0b3") 
        
    #tree
    canvas.draw_line((150, 600), (150, 500), 4, "black")
    canvas.draw_line((150, 500), (130, 525), 4, "black")
    canvas.draw_line((150, 500), (170, 525), 4, "black")
    canvas.draw_line((150, 520), (175, 550), 4, "black")
    canvas.draw_line((150, 520), (125, 550) , 4, "black")
    canvas.draw_line((150, 540), (180, 575), 4, "black")
    canvas.draw_line((150, 540), (120, 575), 4, "black")
   
    #moon
    global x
    canvas.draw_circle((x, 90), 50, 1, "white", "white") 
    x = x + 1
    if x > 650:
        x = -50
        
   #snow layer 3
    for i in range(0,7):
        xRan = random.randint(0, width)
        yRan = random.randint(0, height)
        canvas.draw_circle((xRan, yRan), 2, 1, "white", "white")
        
    

  
frame = simplegui.create_frame("Animation", 600, 600)
frame.set_draw_handler(draw_handler)
frame.start()
