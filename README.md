# minority_rpg
import turtle
import time
world = turtle.Screen()
protag_1 = 'protag_2.gif'
protag_2 = 'protag_1b.gif'
protag_3 = 'protag_3.gif'
protag_4 = 'protag_4.gif'
route1 = 'Area1.gif'
world.addshape(protag_1)
world.addshape(protag_2)
world.addshape(protag_3)
world.addshape(protag_4)
world.addshape(route1)
world.bgpic(route1)
world.screensize(640, 640)
class Protag(turtle.Turtle):

    def __init__(self):
        turtle.Turtle.__init__(self)
        self.penup()
        self.shape(protag_1)
        self.speed = 10

    def walkforward(self):
        self.setheading(90)
        self.shape(protag_3)
        self.forward(self.speed)
        time.sleep(0.1)
        self.shape(protag_4)

    def walkbackward(self):
        self.setheading(270)
        self.shape(protag_2)
        self.forward(self.speed)
        time.sleep(0.1)
        self.shape(protag_1)

    def turnleft(self):
        self.setheading(180)
        self.forward(self.speed)

    def turnright(self):
        self.setheading(0)
        self.forward(self.speed)

""""class World(turtle.Screen()):
    def __init__(self):"""""

protag = Protag()

turtle.listen()
turtle.onkey(protag.turnleft, "Left")
turtle.onkey(protag.turnright, "Right")
turtle.onkey(protag.walkforward, "Up")
turtle.onkey(protag.walkbackward, "Down")

turtle.mainloop()

