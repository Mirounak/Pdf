Experiment 4: Inheritance (Generalization, Specialization & Polymorphism) 
1.  Create a new file Forms.php containing the definitions of two classes: Square and Triangle, each with a $color property initialized with the string 'black'. 2.  Both classes should include a method to read the value of the $color property (getColor()). 3.  Each class must implement a specific getArea() method: o  Square
: pow($length, 2) o  Triangle
: 0.5 * $base * $height 4.  Create a new abstract class named Shape that groups together common information from both classes; the property $color and the method getColor(). 5.  Since Shape is not meant to be instantiated, declare it as abstract. 6.  Add a new class named Circle that extends Shape. Instantiate it and call its getColor() and getArea()
 methods. 7.  Since all subclasses implement their own version of getArea(), declare getArea() as an abstract method in Shape. 8.  Implement the getArea() method in Circle using the formula: pi() * pow($radius, 2
