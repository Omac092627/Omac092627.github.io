# OOP Principals


Polymorphism is often referred to as the third pillar of object-oriented programming, after encapsulation and inheritance. Polymorphism is a Greek word that means "many-shaped" and it has two distinct aspects:

At run time, objects of a derived class may be treated as objects of a base class in places such as method parameters and collections or arrays. When this polymorphism occurs, the object's declared type is no longer identical to its run-time type.
Base classes may define and implement virtual (Links to an external site.) methods, and derived classes can override (Links to an external site.) them, which means they provide their own definition and implementation. At run-time, when client code calls the method, the CLR looks up the run-time type of the object, and invokes that override of the virtual method. In your source code you can call a method on a base class, and cause a derived class's version of the method to be executed.
 

Abstraction means hiding the unnecessary details from type consumers.
Encapsulation means that a group of related properties, methods, and other members are treated as a single unit or object.
Inheritance describes the ability to create new classes based on an existing class.
Polymorphism means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.