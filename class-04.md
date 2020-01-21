HTML:
  Links:
    url means Uniform Resource Locator
  
  Examples:
    a means to link = using the a tag links in html
    href="" is the reference to where you are going

    Absolute url = links to another website
    Relative url = links to another file in the same page

    Directory structure:
      Top folder is root and contains all files.
      Relationships are parent folder, followed by child.
      Homepages are the index.html homepage.

  Layout:
    Block level elements start on a new line 
    Inline elements flow in between surrounding text
    Containing elements are blocks that sit on one another

    3 types of CSS positioning schemes

    Normal flow: they don't sit next to eachother but flow vertically down the page
    
    Relative positioning: moves the position away from normal flow: top, right, bottom, etc

    Absolute positioning: in relation to its own element. will move as the user scrolls up and down the page.

    fixed position: same as absolute, doesn't move when user scrolls up and down

    floating element: position to far left or right. Becomes box element which text can flow around.

    Z-index allows you to control which box sits on top

    960 grid system:
      stylesheet for creating columns
    
JAVA:
  Function:
    functions consist of a series of statements that have been grouped together to perform a specific task.

  Methods:
    are same as functions but have been created inside and are a part of the object.

  Objects: models of real world that have properties and methods.

  Built-in objects are built into the browser and act as a toolkit.

  Parameters are pieces of information passed through a function.
  Statements end with a ";"
  Return value: when you write a function and expect it to return a value.

  Declaring a function:
    Declare a function using the function keyword, give it a name, or identifier followed by (). Statements perform the task sit in the code block.

    Example:
      function sayHello() {
        document.write('Hello')
      }
        (call the function) sayHello();

    Declaring function that needs information - (in brackets are called parameters)
      function getArea(width,height){
        return width * height;
      }

    Calling functions that need information
      as a value = getArea(3,5)
      as a variable = 
        wallWidth = 3
        wallHeight = 5
        getArea (wallWidth, wallHeight)
        
        Above function uses arguments