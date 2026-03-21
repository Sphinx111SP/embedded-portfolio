## Objective
To generate a geometry calculator using python 

### Source code 
```python
import math

class Shape:
    def area(self):
        
        pass
class Circle(Shape):
    def __init__(self,radius):
        self.radius =radius
    def area(self):
        return math.pi * self.radius ** 2
class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side ** 2
class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width
class RightTriangle(Shape):
    def __init__(self, base, height):
        self.base = base
        self.height = height

    def area(self):
        return 0.5 * self.base * self.height

circle = Circle(5)
square = Square(4)
rectangle = Rectangle(6, 3)
triangle = RightTriangle(8, 5)

print("Circle area:", circle.area())
print("Square area:", square.area())
print("Rectangle area:", rectangle.area())
print("Right Triangle area:", triangle.area())
```

### Execution output
```
Circle area: 78.54
Square area: 25
Rectangle area: 24
Triangle area: 12.0
```