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
