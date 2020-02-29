# CODE 201 READING NOTES


> This is my first website using markdown for my reading notes. I'm glad I figured it out.








**TABLE OF CONTENTS:**
  




- [ ] **Monday**
    3. class-03.md
      Javascript: Chapter 4 Decisions and Loops

Type coercision: Javascript runs data behind the scenes.

Falsy: values are teated as if false

truthy: values are treated as if they are true. Almost everything that is not in the falsy table is true.

unary operator: returns a result with just one operand.

Loop checks a condition, if true a block of code will run.

For loop: if you need to run your code a specific number of times.

While loop: if you don't know how many times you need your code to run. The condition doesn't have to be a counter, it will run as long as needed.

Do while loop: is same as a while loop but always runs code in the brackets one time.

Loop counter:

Initialization:
  Create a variable and set it to 0
  var i = 0

Condition:
  i < 10
  Loop should run until counter reaches number

Update:
  i++
  every time the loop runs you add one to the counter.


HTML: Boxes, Borders, Padding

Box Dimensions:
  width, height

Limiting width:
  smallest size the box is shaped

Border: every box has a border
Margin: outer edge of border
Padding: space between border of box and what's in it
Border-width: thick, medium, thin
Border-style: solid, dashed, double
Border-color: any
Padding: space between content and border
Margin: controls gap between boxes
Border-radius: round corner boxes 80px 50px

REMEMBER: OVERAPI.COM - for psudo code


6. class-06.md
    JAVASCRIPT:

  Example:



    Creating an object: literal notation.
              Liter notation is the easiest and most popular way to create objects.
              The object is the curly braces and their content.
              For example a hotel:

              Example:
          
                var hotel = {
                  name: 'Quay', // the name, rooms, and booked are properties.
                  rooms: 69,
                  booked: 40,
                  
                  checkAvailability: function() {     //this is the method
                    return this.rooms - this.booked;
                  }

                };


    Accessing an object and dot notation:
          You access the properties or methods of an object using dot notation.
          You can also access propterties using square brackets.
         
          To access a property or method of an object you use the name of the object,followed by a period, then the name of the property or method you want to  access. This is known as dot notation. 

          The period is known as the member operator. The property or method on its right is a member of the object on its left. Here, two variables are created to hotel name and number of vacant rooms.

          Example:
                  var hotelName = hotel.name;
                  var roomsFree = hotel.checkAvailability();

                  You can also access the properties of an object (but not its methods) using square bracket syntax. This time the object name is followed by square brackets, and the property name is inside them.

                  var hotelName = hotel['name or property'];

                  This is used when : the name of the property is a numbner (bad practice)
                  A variable is being used in place of the property name.

  

JAVASCRIPT DOM:
      Document Object Model... Code name (DOM)

      The document object model specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window.

      You will hear people call the DOM or document object model an Application Programming Interface or API. User interfaces let humans interact with programs, APIs let programs (and Scripts) talk to each other. The DOM states what your script can ask the browser about the current page, and how to tell the browser to update what is being shown to the user.

      CACHING DOM QUERIES:
        Methods that find elements in the DOM tree are called DOM queries. When you need to work with an element more than once, you should use a variable to store the result of this query.
                Example:

                How to select individual elements:

                        getElementByID('one');
                          Uses the value of an elements id attribute (which should be unique within the page).

                        querySelector()
                          Uses a CSS selector, and returns the first matching element.

                How to select multiple elements:

                        getElementsByClassName()
                          Selects all elements that have a specific value for their class attribute.

                        getElementByTagName()
                          Selecs all elements that have the specified tag name.

                        querySelectorAll()
                          Uses a CSS selector to select all matching elements.

                        parentNode
                          Selects the parent of the current element node.
                        
                        previousSiblin / nextSiblin
                          Selects the previous or next sibling from the DOM tree.

                        firstChild / lastChild
                          Selects the first or last child of the current element.

        NODELISTS: DOM QUERIES THAT RETURN MORE THAN ONE ELEMENT
              When a DOM method can return more than one element, it returns a NodeList(even if it only finds one matching element).

                A NodeList is a collection of element nodes. Each node is given an index number (a number that starts with zero, just like an array).

                There are two ways to select an element from a NodeList:
                  The item() method and array syntax.
                  Both require the index number of the element you want.

                  The item() method:
                    NodeLists have a meethod called item() which will return an individual node from the NodeList. You specify the index number of the element you want as a parameter of the method, inside the paranthesis.
                      Example:
                            var elements = document.getElementsByClassName('hot')
                            if (elements.length >= 1) {
                              var firstItem = elements.item(0);
                            }

                    Array Syntax:
                        Array syntax is preferred over the item() method because it is faster. Before selecting a node from a NodeList, check that it contains nodes. If you repeatedly use the NodeList store it in a variable.

                        You can access individual nodes using square bracket syntax similar to that used to access individual items from an array.

                        You specify the index number of the element you want inside square brackets that follow the NodeList.
                          Example:
                              var elements = document.getElementsByClassName('hot');
                                if (elements.length >= 1) {
                                  var firstItem = elements[0];
                                }

              REPEATING ACTIONS FOR AN ENTIRE NODELIST:
                When you have a NodeList, you can loop through each node in the collection and apply the same statements toe ach.
                  Example:
                        var hotItems = document.querySelectorAll('li.hot');
                        for(var i = 0; i < hotItems.length; i++){
                          hotItems[i].className = 'cool';
                        }

                
              TRAVERSING THE DOM:
                When you have an element node, you can select another element in relation to it using these five properties. This is known as traversing the DOM.
                    parentNode:
                      This property finds the element node for the containing (or parent) element in HTML. If you started the first <li> element, then its parent node would be the one representing the <ul> element.

                    previousSiblin/nextSibling:
                      These properties find the previous or next sibloing of a node if there are any siblings.
                      If you started with the first <li> element, it would not have a previous sibling. However, its next sibling would be the node representing the second <li>.

                    firstChild/lastChild:
                      These properties find the first or last child of the current element.
                      If you started with the <ul> element, the first child would be the node representing the first <li> element, and the last child would be the last <li>.


              ADDING OR REMOVING HTML CONTENT:
                There are two very different approaches to adding and removing content from a DOM tree: the innerHTML property and DOM manipulation.


                THE innerHTML PROPERTY (there are security risks associated with using this method)
                *must use a string*
                innerHTML can be used on any element node. It is used both to retrieve and replace content.
                  Example:
                        var item;
                        item = '<em> Fresh</em> figs';


                DOM MANIPULATION METHODS: 
                  DOM manipulation refers to a set of DOM methods that allow you to create element and text nodes, and then attach them to the DOM tree or remove them from the DOM tree.
                      Example:
                              create new text node
                              create new element node
                              Add text node to element node
                              select element you want to add the new fragment to
                              Append the new fragment to the selected element 


                ADDING ELEMENTS USING DOM MANIPULATION:
                  This is an alternative to innerHTML.
                  createElement()
                    start by creating a new element node
                  createTextNode()
                    create a new text node
                  appendChild()       
                    add it to the DOM tree using the appendChild() method.
                      Example:
                              var newEl = document.createElement('li');
                                create a new element and store it in a variable

                              var newText = document.createTextNode('quinoa');
                                create a text node and store it in a variable

                              newEl.appendChild(newText);
                              attach the new text node to the new element

                              var position = document.getElementsByTagName('ul')[0];
                                find the position where the new element should be added

                              position.appendChild(newEl);     
                                insert the new element into its position


              REMOVING AN ELEMENT FROM THE DOM TREE:
                  Example:
                          var removeEl = document.getElementsByTagName('li')[3];
                            the element to remove

                          var containerEl = removeEl.parentNode;
                            its containing element

                          containerEl.removeChild(removeEl);
                            removing the element


              ATTRIBUTE NODES:
                  Once you have an element node, you can use other properties and methods on that element node to access and change its attributes.

                  There are two steps to accessing and updating attributes. First select the element node that carries the attribute and follow it with a period symbol. 

                      Example:
                              document.getElementById('one').getAttribute('class');

                              getAttribute() gets the value of an attribute
                              hasAttribute() checks if element node has a specified attribute
                              setAttribute() sets the value of an attribute
                              removeAttribute() removes an attribute from an element node


    HTML:
  CHART JS
    What is it?
        Chart JS is a library that's used in javascript to make my life easier.

      INTEGRATION
        Chart.js can be integrated with plain JavaScript or with different module loaders. The examples below show how to load Chart.js in different systems.

        THE GRID
            Before we can start drawing, we need to talk about the canvas grid or coordinate space. Our HTML skeleton from the previous page had a canvas element 150 pixels wide and 150 pixels high. To the right, you see this canvas with the default grid overlayed. Normally 1 unit in the grid corresponds to 1 pixel on the canvas. The origin of this grid is positioned in the top left corner at coordinate (0,0). All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y). Later in this tutorial we'll see how we can translate the origin to a different position, rotate the grid and even scale it, but for now we'll stick to the default.


        Drawing rectangles
          Unlike SVG, <canvas> only supports two primitive shapes: rectangles and paths (lists of points connected by lines). All other shapes must be created by combining one or more paths. Luckily, we have an assortment of path drawing functions which make it possible to compose very complex shapes.

          First let's look at the rectangle. There are three functions that draw rectangles on the canvas:

          fillRect(x, y, width, height)
          Draws a filled rectangle.
          strokeRect(x, y, width, height)
          Draws a rectangular outline.
          clearRect(x, y, width, height)
          Clears the specified rectangular area, making it fully transparent.
          Each of these three functions takes the same parameters. x and y specify the position on the canvas (relative to the origin) of the top-left corner of the rectangle. width and height provide the rectangle's size.


          The fillRect() function draws a large black square 100 pixels on each side. The clearRect() function then erases a 60x60 pixel square from the center, and then strokeRect() is called to create a rectangular outline 50x50 pixels within the cleared square.

          Drawing paths
            Now let's look at paths. A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, we take some extra steps:

            First, you create the path.
            Then you use drawing commands to draw into the path.
            Once the path has been created, you can stroke or fill the path to render it.
            Here are the functions used to perform these steps:

            beginPath()
            Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.
            Path methods
            Methods to set different paths for objects.
            closePath()
            Adds a straight line to the path, going to the start of the current sub-path.
            stroke()
            Draws the shape by stroking its outline.
            fill()
            Draws a solid shape by filling the path's content area.
            The first step to create a path is to call the beginPath(). Internally, paths are stored as a list of sub-paths (lines, arcs, etc) which together form a shape. Every time this method is called, the list is reset and we can start drawing new shapes.

            Moving the pen
                One very useful function, which doesn't actually draw anything but becomes part of the path list described above, is the moveTo() function. You can probably best think of this as lifting a pen or pencil from one spot on a piece of paper and placing it on the next.

                moveTo(x, y)
                Moves the pen to the coordinates specified by x and y.
                When the canvas is initialized or beginPath() is called, you typically will want to use the moveTo() function to place the starting point somewhere else. We could also use moveTo() to draw unconnected paths. Take a look at the smiley face below.

                To try this for yourself, you can use the code snippet below. Just paste it into the draw() function we saw earlier.


          Lines
            For drawing straight lines, use the lineTo() method.

            lineTo(x, y)
            Draws a line from the current drawing position to the position specified by x and y.
            This method takes two arguments, x and y, which are the coordinates of the line's end point. The starting point is dependent on previously drawn paths, where the end point of the previous path is the starting point for the following, etc. The starting point can also be changed by using the moveTo() method.


          Bezier and quadratic curves
              The next type of paths available are Bézier curves, available in both cubic and quadratic varieties. These are generally used to draw complex organic shapes.

              quadraticCurveTo(cp1x, cp1y, x, y)
              Draws a quadratic Bézier curve from the current pen position to the end point specified by x and y, using the control point specified by cp1x and cp1y.
              bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)
              Draws a cubic Bézier curve from the current pen position to the end point specified by x and y, using the control points specified by (cp1x, cp1y) and (cp2x, cp2y).
              The difference between these can best be described using the image on the right. A quadratic Bézier curve has a start and an end point (blue dots) and just one control point (indicated by the red dot) while a cubic Bézier curve uses two control points.

              The x and y parameters in both of these methods are the coordinates of the end point. cp1x and cp1y are the coordinates of the first control point, and cp2x and cp2y are the coordinates of the second control point.

              Using quadratic and cubic Bézier curves can be quite challenging, because unlike vector drawing software like Adobe Illustrator, we don't have direct visual feedback as to what we're doing. This makes it pretty hard to draw complex shapes. In the following example, we'll be drawing some simple organic shapes, but if you have the time and, most of all, the patience, much more complex shapes can be created.

              There's nothing very difficult in these examples. In both cases we see a succession of curves being drawn which finally result in a complete shape.

    class-14.md
         CSS Transforms, Transitions, and Animations

2D Rotate
The transform property accepts a handful of different values. The rotate value provides the ability to rotate an element from 0 to 360 degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically. Later we will discuss how you can change this default point of rotation.

2D Scale
Using the scale value within the transform property allows you to change the appeared size of an element. The default scale value is 1, therefore any value between .99 and .01 makes an element appear smaller while any value greater than or equal to 1.01 makes an element appear larger.

2D Translate
The translate value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document. Using the translateX value will change the position of an element on the horizontal axis while using the translateY value will change the position of an element on the vertical axis.

As with the scale value, to set both the x and y axis values at once, use the translate value and declare the x axis value first, followed by a comma, and then the y axis value.

The distance values used within the translate value may be any general length measurement, most commonly pixels or percentages. Positive values will push an element down and to the right of its default position while negative values will pull an element up and to the left of its default position.

2D Skew
The last transform value in the group, skew, is used to distort elements on the horizontal axis, vertical axis, or both. The syntax is very similar to that of the scale and translate values. Using the skewX value distorts an element on the horizontal axis while the skewY value distorts an element on the vertical axis. To distort an element on both axes the skew value is used, declaring the x axis value first, followed by a comma, and then the y axis value.%p

The distance calculation of the skew value is measured in units of degrees. Length measurements, such as pixels or percentages, do not apply here.

You may combine these transformations to make them work as well. 

Transform Origin
As previously mentioned, the default transform origin is the dead center of an element, both 50% horizontally and 50% vertically. To change this default origin position the transform-origin property may be used.

The transform-origin property can accept one or two values. When only one value is specified, that value is used for both the horizontal and vertical axes. If two values are specified, the first is used for the horizontal axis and the second is used for the vertical axis.

Individually the values are treated like that of a background image position, using either a length or keyword value. That said, 0 0 is the same value as top left, and 100% 100% is the same value as bottom right. More specific values can also be set, for example 20px 50px would set the origin to 20 pixels across and 50 pixels down the element.

Perspective
In order for three-dimensional transforms to work the elements need a perspective from which to transform. The perspective for each element can be thought of as a vanishing point, similar to that which can be seen in three-dimensional drawings.

The perspective of an element can be set in two different ways. One way includes using the perspective value within the transform property on individual elements, while the other includes using the perspective property on the parent element residing over child elements being transformed.

Using the perspective value within the transform property works great for transforming one element from a single, unique perspective. When you want to transform a group of elements all with the same perspective, or vanishing point, apply the perspective property to their parent element.

The example below shows a handful of elements all transformed using their individual perspectives with the perspective value.

Transitions
As mentioned, for a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the :hover, :focus, :active, and :target pseudo-classes.

There are four transition related properties in total, including transition-property, transition-duration, transition-timing-function, and transition-delay. Not all of these are required to build a transition, with the first three are the most popular.

In the example below the box will change its background color over the course of 1 second in a linear fashion.

Transition Duration
The duration in which a transition takes place is set using the transition-duration property. The value of this property can be set using general timing values, including seconds (s) and milliseconds (ms). These timing values may also come in fractional measurements, .2s for example.

When transitioning multiple properties you can set multiple durations, one for each property. As with the transition-property property value, multiple durations can be declared using comma separated values. The order of these values when identifying individual properties and durations does matter. For example, the first property identified within the transition-property property will match up with the first time identified within the transition-duration property, and so forth.

If multiple properties are being transitioned with only one duration value declared, that one value will be the duration of all the transitioned properties.



  
- [ ] **Tuesday**
   
   2. class-02.md
     
     - Java Script:
         
         Evaluations: You can analyze values in a script to determine the expected results.
          
          Decisions: Using results of evaluations you can determine which path your script goes down.

          Loops: perform some steps repeatedly.
          
          When using Decision Making you want to use flow charts.
          
          Evaluating conditions and conditional statements: 2 components to a decision:
          
            An expression is evaluated, which returns a value.
            
            A conditional statement says what to do in a given situation.
      Example:
      
          Comparison operators: <,>,*,!=,===
          
          Logical operators: &&, ||, !
          
          Switch Statements: can pass multiple cases (variables) through one statement, basically only runs when called.
          
            Example: Switch(level) {
                      case 'One':
                       title = 'level1';
                       break; (this stops the code from running)
                       
          If statements: if you need to compare values to get a result.
          
            Example: if(score>50) {
                      congratulate();
                      }
                        else {
                        encourage();
                        }
       - HTML:
          Structural markup: describe headings and paragraphs.
          
          Semantic markup: used for emphasis.
          
          h1: main heading
          
          h2: subhead
          
          h3: smaller
          

          
        . CSS:
        
            External CSS:
            
              <link>: tell browswer where css is, goes in the head
              
              href: specifies path to folder
              
              type: type of document
              
              rel: relationship to file
              
                Example: <link href="CSS/Styles.css" type="text/css" rel="stylesheets"/>
          
          Internal CSS:
          
              <style></style>
          
          CSS Selectors:
          
            Universal Selectors: applies to all elements in the document: *{}
            
            type selector: matches element names: h1, h2, h3 {}
            
            class selector: matches class with period: .note{}
            
            ID Selector: #introduction {}
            
            Child Selector: li>a{}
            
            Descendant Selector: p a {}
            
            adjacent sibling selector: h1+p {}
            
            general sibling selector: h1~p {}



    class-04.md
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

    
  class-13.md
    THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS
  A native client application is one that is installed on a user's computer or device. Examples of such an application include, but is not limited to, WinForms, WPF, Windows Store, Windows Phone, and iOS applications.

  Cookies are included with every HTTP request, therby slowing down your web application by needlessly transmitting the same data over and over. 

  Cookies are included with every HTTP request, thereby sending data unencrypted over the internet(unless served over an SSL).

  Cookies are limited to about 4kb of data - enough to slow down your application, but not enough to be terribly useful.

  What we really want is:
    A lot of storage space 
    On the client
    that persists beyond a page refresh
    and isn't transmitted to the server

    HTML5 STORAGE:
      It's web storage, or local storage or DOM storage.

      It's a way for web pages to store named key/value pairs locally, within the client web browsers. Like cookies, this data persists even after you navigate away from the website, close your browser tab, exit your browser, or what have you. Unlike cookies, this data is never transmitted to the remote web server -unless sent manually. It is implemented natively in web browsers, so it is available even when third-party browser plugins are not.

      FROM YOUR JAVASCRIPT CODE:
        You'll acess HTML storage through the localstorage object on the global window object. Before you can use it, you should peep whether the browser supports it. 

        how to check for it?
          Example: function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}


//USING HTML5 STORAGE:
  Calling setItem() with a named key that already exists will silently overwrite the previous value. Calling getItem() with a non-existent key will return null rather than throw an exception.

Like other JavaScript objects, you can treat the localStorage object as an associative array. Instead of using the getItem() and setItem() methods, you can simply use square brackets. For example, this snippet of code:

var foo = localStorage.getItem("bar");
// ...
localStorage.setItem("bar", foo);
…could be rewritten to use square bracket syntax instead:

var foo = localStorage["bar"];
// ...
localStorage["bar"] = foo;
            
- [ ] **Wednesday**

- [ ] **Friday**

- [ ] **Saturday**

    1. class-01.md
      - The ABC's of programming helped me gain an idea on how JavaScript functions as a whole. I learned the different pieces that structure a webpage including JavaScript, CSS, and HTML. Each element is different and does something different in order to make the browswer render webpages. JavaScript is one of the most commonly used languages in the world. 
     
     - A few key points that stuck out to me was different functions of JavaScript itself. For example, what an object is and how a computer classifies an object. And how we can use JavaScript to describe and "build" the object. JavaScript also uses the "top down" method which breaks the information into smaller pieces as we go from top to bottom. Starting with the variable and working your way down through functions and methods. Lest not forget, arguments.

    5. class-05.md
    
     HTML:
  Images:
    You should store images on a separate file within your site. 
    When adding images you need a:
      Image tag: is an empty element meaning it doesn't get a closing tag.

      Source tag: This tells the browser where to find it.

      Alt tag: this provides a text description of the image which describes the image if you can not see it.

      Title: You can use a title attribute with the image element to provid additional information about the image.

      Height: This specifies the height of the image. Goes in the Image tag.

      Width: Specifies the width of the image and also goes within the Image tag.

      
      Place images before your paragraph.
      In the middle of your paragraph. 
      Or at the end of your paragraph.

    Align images vertically:
      Top: This aligns first lign of surrounding text with top of image.

      Middle: This aligns the text with the middle of the image.

      Bottom: this aligns first lign of text with bottom of the image. (probably the preferred method)


    TEXT:
      text-transform is the property to change the case of text.

        Uppercase: causes the text to appear uppercase.

        Lowercase: causes the text to appear lowercase.

        Capitalize: capitalizes the first letter of every word.
      
      text-decoration:

        none: this removes any decoration already applied to the text.

        underline: this adds a line underneath the text.

        overline: this adds a line over the top of the text.

        line-through: this adds a line through words.

        blink: this animates the text to make it flash on and off (however this is generally frowned upon, as it is considered rather annoying)

        line-height: space between the lines
        letter-spacing: space between letters
        word-spacing: space between words

        text-align: left, right, center, justify

        vertical-align: aligns the text vertically

        text-indent: indents first line of text

        text-shadow: used to create a drop shadow behind the text

        :LINK, :VISITED - changes the color of link after visited

        hover, active, focus: these allow the user to interact with what they are viewing on your page.


  class-07.md
    Html:
  Basic table structure:
    Tables are instrumental in displaying elements grouped together by tables that flow down the page.
      Tables are indicated with the Example: <table> element. it's used to create a table. The contents of the table are written out row b row.
      Example: <tr> indicates the start of each row using the opening tr tag. it stands for table row. it is followed by one or more td elements one for each cell in that row. At the end of the row you use a closing /tr tag. td is when each cell of a table is represented, stands for table data. At the end you use a closing /td tag. th element is used just like the td element but its purpose is to represent the heading for either a column or a row. the colspan tag is used to stretch across multiple columns. Example: <td colspan="2" the two indicates how many columns to stretch.> This his how you span columns. Spanning rows uses the rowspan tag. Example: <td rowspan="2" and that indicates two rows>. Long tables use: Example: <thead> the headings of the table should be here. <tbody> the body should sit inside here. <tfoot> the foot of the table. to add width you just: Example: <table width="100" cellpadding="10" cellspacing="5"> this is just for width and spacing. For border and background it can go in the table tag or td tag. Example: <table border="2" bgcolor=""> to give a border.


JAVA:
    Creating an object: constructor notation. The new keyword and the object constructor create a blank object. You can then add properties and methods to the object.
      Example: var hotel = new Object(); the constructor is the object function.            hotel.name = 'Quay';
                            hotel.rooms = 40;
                              hotel.booked = 25;
                                hotel.checkAvailability = function(){
                                  return this.rooms - this.booked;
                                }


      CONSTRUCTING MANY OBJECTS: CONSTRUCTOR NOTATION
        Sometimes you will want several objects to represent similar things. Object constructors can use a function as a template for creaqting objects. First, create the template with the objects properties and methods.
          Example: function Hotel(name, rooms, booked){
            this.name = name;
            this.rooms = rooms;
            this.booked = booked;
            this.checkAvailability = function(){
              return this.rooms - this.booked;
            }
          }


          You create instances of the object using the constructor function. The new keyword followed by a call to the function creates a new object.The properties of each object are given as arguments to the function.

              Example: var quayHotel = new Hotel('Quay', 40, 25)
                        var parkHotel = new Hotel('Park', 120, 77)

            
          Literal Notation:
            Example: var hotel = {}

                      hote.name= 'Name'
                      hotel.rooms = 40;
                      hotel.booked = 25
                      hotel.checkAvailability = function(){
                        return this.rooms - this.booked;
                      }

            Object constructor notation:
                Example: var hotel = new Object();
                  hotel.name = 'Name';
                  hotel.rooms = 40;
                  hotel.booked = 25;
                  hotel.checkAvailability = function() {
                    reutrn this.rooms - this.booked;
                  }


      Creating an object with properties and methods
        Literal notation:
            Example: var hotel = {
              name: 'Name',
              rooms: 40,
              booked: 25,
              checkAvailability: function(){
                return this.rooms - this.booked
              }
            }


        Object constructor notation:
          the function can be used to create multiple objects. The this keyword is used instead of the object name.
                Example: function Hotel(name, rooms, booked){
                  this.name = name;
                  this.rooms = rooms;
                  this.booked = booked;
                  this.checkAvailability = function(){
                    return this.rooms - this.booked
                  }
                }
                      var quayHotel = new Hotel ('Quay', 40, 25)
                      var parkHotel = new Hotel ('Park', 120, 77)


          This (it is a keyword)
            The keyword this is commonly used inside functions and objects. Where the function is declarfed alters what this means. it always refers to one object, usually the object in which the function operates.

  class-09.md
    HTML:
  Forms: Traditonally, the term form has referred to a printed document that contains spaces for you to fill in information.
    Form structure: form, action, method.
    Text input: input element is used to create several different form controls.
    Password input for password
    Text area for text
    Radio button which is a button for selecting different items.
    Checkbox to check different items

    Lists, tables, forms
      List markers can be given different appearances using the list style type and list style image properties.
      Table cells can have different borders aqnd spacing in different browsers, but there are properties you can use to control them and make them more consistent.
      Forms are easier to use if the form controls are vertically aligned using css.
      Forms benefit from styles that make them more interactice.


- [ ] **Sunday**

class-10.md
JAVASCRIPT:
  Execution context:
    Every statement in a script lives in one of three execution contexts:
      Global context: code that is in the script but not in a function. There is only one global context in any page.

      Function Context: 
        Code that is being run within a function.

      Eval context:
        Text is executed like code in an internal function.


      The Stack:
        The javascript interpreter processes one line at a time. When a statement needs data from another function, it stacks or piles the new function on top of the current task.

      Error Objects:
          When an error object is created, it will contain the following properties:
            Name: type of execution.
            Message: Description
            fileNumber: Name of the javascript file
            lineNumber: line number of error.

      There are seven types of built-in error objects in javascript. You'll see them on the next two pages:
          Error: generic error - the other errors are all based upon this error
          SyntaxError: Syntax has not been followed
          ReferenceError: tried to reference a variable that is not declared
          TypeError: An unexpected data type that cannot be coerced
          RangeError: Numbers not in acceptable range
          URIError: encodeURI(), decodeURI(), and similar methods used incorectly
          EvalError: eval () function used incorrectly



          HTML: 

  The reading notes provided were about Images and Practical information.
    The image section described the different techniques in order to position images in the way that you want them to be structured. From background images, to centering them, sky's the limit.

    As for practical information. The information seemed to be geared toward understanding how your page can get more traffic and how you can track who is viewing your information. You can use an FTP to transfer your files from your IDE to a hosting site. There are more tools and tips but these were just some of the takeaways that I found useful.
