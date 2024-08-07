# POLYGONES-AVEC-TURTLE



import turtle
import random
import math

def polygone_turtle(sides, x, y, radius, color):
    angle = 360 / sides
    side_length = 2 * radius * math.sin(math.pi / sides)

    turtle.penup()
    turtle.goto(x, y - radius)
    turtle.pendown()
    turtle.color(color)
    turtle.begin_fill()

    for _ in range(sides):
        turtle.forward(side_length)
        turtle.left(angle)

    turtle.end_fill()

def main():
    turtle.speed(0)
    turtle.hideturtle()
    turtle.bgcolor("white")
    
    colors = ["black", "blue", "red", "green", "yellow"]
    for color in colors:
        sides = random.randint(3, 10)
        x = random.randint(-200, 200)
        y = random.randint(-200, 200)
        radius = random.randint(20, 100)
        
        polygone_turtle(sides, x, y, radius, color)
    
    turtle.done()

if __name__ == "__main__":
    main()

