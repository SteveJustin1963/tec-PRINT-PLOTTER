# tec-PRINT-PLOTTER
- TE 12 pg 30
- https://github.com/SteveJustin1963/tec-BOOKS/blob/master/TE/Mag/talking_electronics_12.pdf

![](https://github.com/SteveJustin1963/tec-PRINT-PLOTTER/blob/main/pics/TinyTake_26-03-2022-11-10-02.png)


## x,y plotter, how does it work?

This TE project controls the `VT200 pen/Plotter` to print by plotting text or images. The xy plotter is a mechanical device that allows you to draw lines and shapes on a piece of paper. The plotter is made up of two parts: the x-axis and the y-axis. The x-axis is a horizontal line that runs across the paper, and the y-axis is a vertical line that runs up and down the paper. To use the plotter, you first need to find the point where the x-axis and the y-axis intersect. This point is called the origin. The plotter will then move the pen to this point. Next, you need to choose the direction in which you want to draw your line. To do this, you need to specify the x and y coordinates of the end point of the line. The plotter will then draw the line from the origin to the end point. "All information is fed to the printer in ASCII code. If you want a particular character, the correct code must be sent to the printer. Even if you want to send a number to the printer, such as 150, you must send it in the form of ASCII. This means 150 translates to 31 35 30, as you will see later from the table." The addition of the ROM in the circuit is to save the operator from typing in ascii control codes to get control control of the printer from the tec-1’s hexpad. The data still needs to be stored in ram from #0800 but the printer control is run from rom at #1880.

![](https://github.com/SteveJustin1963/tec-PRINT-PLOTTER/blob/main/pics/ascii-1.png)

also can generate graphics on the printer and information is still in ASCII. 
eg using the table code looks like this:
```
OA = LF = Line Feed.
OD = CR = Carriage Return
12 =. DC2 = Graphic Mode
49 = I = sets the pen's location as coordinates 0,0.
2C = , =Separates I from D
44 = D = draw from present location to the coordinate given by the next byte(s) of data.
```


### Iterate

Unfortainly in 2022 its in extremely unlikely one can buy a VT200 pen/Plotter. So we can either seek a near current pen plotter that takes 8 bit input or we make our own x y plotter, which will need an interpreter and motor control routines. It is possible we could just use a raw dc drive or stepper drive xy plotter, or even use a scientific plotter that take direct analog voltages. We will explore these possibilities. tba. 

maybe do something like in ref.

![](https://github.com/SteveJustin1963/tec-PRINT-PLOTTER/blob/main/pics/pp1.png)




### Ref
- https://www.benjaminpoilve.com/projects/plotter-story.html#
- https://github.com/BenjaminPoilve/Liplo




