from tkinter import *
import time
import random

window = Tk()
window.title('To avoid an objects')
canvas = Canvas(window, width=800, height=600, bg='white')
canvas.pack(padx=10,pady=10)
#The velocity
vx = 10.0
vy = 5.0 
# Boundaries
x_min = 0.0
y_min = 0.0
x_max = 800.0
y_max = 600.0
robot=canvas.create_rectangle(0,10,30,30,fill='red')
Obx1=random.randint(75,250)
Oby1=random.randint(75,250)
Obx2=Obx1+550
Oby2=Oby1-75
#count for steps to move away from the objects
count=0
#create object to avoid
obj1=canvas.create_rectangle(Obx1,Oby1,Obx2,Oby2, fill='green')
#Generate x and y coordinates for 1000 timesteps
for t in range(1, 1000):
    x1,y1,x2,y2=canvas.coords(robot)
#robot to Detect left side of object
    if x2>(Obx1 - 10) and x2<(Obx1+10) and y1< Oby1 and y1>Oby2:
        count=5
#robot to Detect right side of object
    if x1<(Obx2 + 10) and x1>(Obx2 - 10) and y1< Oby1 and y1>Oby2:
        count=5
#robot to Detect Bottom of object
    if y1>(Oby1 - 10) and y1<(Oby1+10) and x1>Obx1 and x1<Obx2:
        count=5
#robot to Detect top of object
    if y1>(Oby2 - 10) and y1<(Oby2+10) and x1>Obx1 and x1<Obx2:
        count=5
#if counter set move away from left side or bottom of object
    if count>0:
        vx=-10
        vy=5
        count=count-1
    
# If a boundary has been crossed, reverse the direction
    if x1 >= x_max:
        vx = -10.0
    if y1 <= y_min:
        vy = 5.0
    if y2 >= y_max:
        vy = -5.0
    if x1 <= x_min:
        vx = 10.0
# Reposition the robot
    canvas.coords(robot,x1+vx,y1+vy,x2+vx,y2+vy)
    canvas.update()
# Pause for 0.1 seconds, then delete the image
    time.sleep(0.1)
window.mainloop()
