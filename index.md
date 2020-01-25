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



- [ ] **Sunday**
