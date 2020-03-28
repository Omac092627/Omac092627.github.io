CLASS01:
SMACSS
SCALABLE MODULAR CSS

BASE || LAYOUT || MODULES || THEME

RESPONSIVE DESIGN: ADJUST THE SCREEN OR LAYOUT CHANGES. CONTENT MUST ALWAYS STAY THE SAME. 
    DESKTOP TO MOBILE.

BLOCK ELEMENT TAKE ALL SPACE THEY CAN
INLINE ELEMENT TAKE WHAT THEY NEED - CONTENT

YOUR BRAIN CAN ONLY PROCESS SO MUCH. ONLY SO MUCH INFORMATION CAN BE DISPLAYED, SO COLUMNS ARE NECESSARY. 

THEME INVOLVES SPACE
MAKE A SITE DESIGN THAT EVERY PAGE SHARES. 

MEDIA QUERY = //@media(min-width: 960px){
    div{

    }
}

RESET
BASE : core, font, reset, box sizing
LAYOUT: spacing, position
MODULES: rotators
THEME: feels

CLASS02:
JQUERY

jquery IS A JAVASCRIPT FILE THAT YOU INCLUDE IN YOUR WEB PAGES. iT LETS YOU FIND ELEMENTS USING CSS-STYLE SELECTORS AND THEN DO SOMETHING WITH THE ELEMENTS USING JQUERY METHODS.

1. Find elements using css-style selectors

//$() is often used as a shorthand to save typing jquery() as shown here//
//$('li.hot') grabs list elements with a class of hot//


JQUERY object has many methods that you can use to work with the elements you select. The methods represent tasks that you commonly need to perform with elements.

DO SOMETHING WITH THE ELEMENTS USING JQUERY METHODS:
    //$('li.hot').addClass('complete');


WHY USE JQUERY?
    1. simple selectors, jquery uses a language that is already familiar to front-end web developers: css selectors. 
        They are much faster at selecting elements
        more accurate
        require less code
        Are already used by most front-end developers


FINDING ELEMENTS: AKA: CHEAT SHEET

BASIC SELECTORS:
    * selects all elements
    element: all elements with that element name
    #id: elements whose id attribute has the value specified
    .class: elements whose class attribute has the value specified
    selector1, selector2: method, which is more efficient when combining selections

HIERARCHY:
    ancestor descendant: an element that is a descendant of another element
    parent>child: an element that is a direct child of another element
    previous+next: adjacent sibling selector only selects elements that are immediately followed by the previous element.

BASIC FILTERS
    :not(selector) : all elements except the one in the selector(e.g., div:not('#summary')
    :first : the first element from the selection
    :last : the last element from the selection
    :even : elements with an even index number in the selection
    :odd : elements with an odd indes number in the selection
    :eq(index) : elements with an index number equal to the one in the parameter
    :gt(index) : elements with an index number greater than the parameter
    :lt(index) : elements with an index number less than the parameter
    :header : all <h1> - <h6> elements
    :animated : elements that are currently being animated
    :focus : the element that currently has focus

CONTENT FILTERS
    :contains : elements that contain the specified text as a parameter. 
    :empty : all elements that have no children
    :parent : all elements that have a child node 
    :has(selector) : elements that have at least one element that matches the selector.

VISIBILITY FILTERS: 
    :hidden : all elements that are hidden
    :visible : all elements that consume space in the layout of the page. 

CHILD FILTERS:
    :nth-child(expr) the value here is not sero-based e.g. ul li:nth-child(2)
    :first-child first child from the current selection
    :last-child last child from the current selection
    :only-child when there is only one child of the element

ATTRIBUTE FILTERS
    [attribute] Elements that carry the specified attribute 
    [attribute='value'] elements that carry the specified attribute with the specified value
    [attribute!='value'] elements that carry the specified attribute but not the specified value
    [attribute^='value'] the value of the attribute that begins with this value
    [attribute='value'] the value of the attribute ends with this value
    [attribute*='value'] the value should appear somewhere in the attribute value
    [attribute|='value'] equal to given string, or starting with string and followed by a hyphen
    [attribute~='value] the value should be one of the values in a space separated list
    [attribute][attribute2] elements that match all of the selectors

FORM
    :input : all input elements 
    :text : all text inputs
    :password : all password inputs
    :radio : all radio buttons
    :checkbox : all checkboxes
    :submit : all submit buttons
    :image : all image tags
    :reset : all reset buttons
    :button : all button elements
    :file : all file inputs 
    :selected : all selected items from dropdown menu
    :enabled all enabled for elements 
    :disabled all disabled form elements
    :checked all checked radio buttons or boxes

SINGLE ELEMENT
    If a selector returns one element, the jquery object contains a reference to just one element node
        //$('ul')//

MULTIPLE ELEMENTS 
    If a selector returns several elements the jquery object contains references to each element
        //$('li')//

GET INFORMATION
    //var content = $('li').html();// use .html() to get information

SET INFORMATION
    //var content = $('li').html('Updated')// updates the content

JQUERY OBJECTS STORE REFERENCES TO ELEMENTS
CACHING JQUERY SELECTIONS IN VARIABLES:
    //$listItems = $('li');// put a $ in front of variable to differentiate


CHECKING A PAGE IS READY TO WORK WITH:
    //$(document).ready(function(){
        //your script goes here
        //when the page is ready it runs the code in here
    })


THE LOAD EVENT
    jquery had a .load() method it fired on the load event, but has been replaced by the .on(). You should use this if it needs to know the assets have loaded, or if for example you need the dimensions of an image.

THE .ready() METHOD
    checks if the browser supports the DOM content loaded event, because it fires as soon as the DOM has loaded and can make the page appear as if loading faster.

PLACING SCRIPTS BEFORE THE CLOSING /body TAG
    when you place your script at the end of the page, the html will have loaded into the DOM before the script runs.
    You will, however, still people using the .ready() method because scripts that use it still work if someone moves the script tag elsewhere in the html page.

GETTING ELEMENT CONTENT
    //.html() only retrieves the html inside the first element in a matched set along with its decendants
    //.text() is used to to retrieve text from a jquery selection, it returns the content from every element in the jquery selection, along with the text from any decendants

INSERTING ELEMENTS
    CREATING THE NEW ELEMENTS IN A JQUERY OBJECT
    USE A METHOD TO INSERT THE CONTENT INTO THE PAGE

    1. CREATING NEW ELEMENTS IN A JQUERY OBJECT
        //var $newFragment = $('<li>');// this creates a new variable
        //var $newItem = $('<li class="new">item</li>); this creates a variable and stores a jquery object in it. this jquery object in turn contains an <li> element.

    2. ADDING THE NEW ELEMENTS TO THE PAGE
        Once you have a variable holding the new content, you can use the following methods to add the content to the DOM TREE.

        .before() this method inserts content before the selected elements.
        .after() this method inserts content after the selected elements.
        .prepend() this method inserts content inside the selected elements after the opening tag. 
        .append() this method inserts content inside the selected elements before the closing tag.

GETTING AND SETTING ATTRIBUTES
    .attr() this method can get or set a specified attribute and its value. To get the value of an attribute, you specify
        //$('li#one').attr('id');
        //$('li#one').attr('id','hot');

    .removeAttr() this method removes a specified attribute. You just specify the name of the attribute that you want to remove from the element in the parenthesis.
        //$('li#one').removeAttr('id');

    .addClass() this method adds a new value to the existing value of the class attribute. It does not overwrite existing values.
    .removeClass() this method removes a value from the class attribute, leaving any other class names within the attribute intact.

HOW TO GET A CSS PROPERTY
    //var backgroundColor = $('li').css('background-color');//
HOW TO SET A CSS PROPERTY
    //$('li').css('background-color', '#272727');
    when dealing with dimensions that are specified in pixels, you can increase and decrease the values using the += and -= operators.
    //$('li').css('padding-left', '+=20')
SETTING MULTIPLE PROPERTIES
    you can set multiple properties using object literal notation:
        Properties and values are placed in curly braces
        A colon is used to separate property names from their values
        A comma separates each pair
        
        $('li').css({
            'background-color': '#272727',
            'font-family': 'Courierr'
        })

WORKING WITH EACH ELEMENT IN A SELECTION
    JQUERY ALLOWS YOU TO RECREATE THE FUNCTIONALITY OF A LOOP ON A SELECTION OF ELEMENTS, USING .EACH() METHOD.
        .each() allows you to perform one or more statements on each of the items in the selection of elements that is returned by a selector - rather like a loop in javascript.

        this or $(this) as the .each() method goes through the elements in a selection, you can access the current element using the this keyword.

EVENT METHODS
    the .on() method is used to handle all events. Behind the scenes, jquery handles all of the cross-browser isses you saw in the last chapter.

    $('li').on('click', function(){
        $(this).addClass('complete');
    })

THE EVENT OBJECT
    EVER EVENT HANDLING FUNCTION RECEIVES AN EVENT OBJECT. IT HAS METHODS AND PROPERTIES RELATED TO THE EVENT THAT OCCURRED. 
        $('li').on('click' function(e){
            eventType = e.type
        })

ADDITIONAL PARAMETERS FOR EVENT HANDLERS
    .on(events[, selector][, data], function(e))
        click   

AJAX - ASYNCHRONOUS JAVASCRIPT AND XML AKA JQUERY

CLASS03:
FLEXBOX AND TEMPLATING

    Javascript Templating Language and Engine -- Mustache.js with Node and Express

        Javascript Templating:
            is a fast and efficient technique to render client-side view templates with Javascript by using a JSON data source. THE TEMPLATE IS html MARKUP, WITH ADDED TEMPLATING TAGS THAT WILL EITHER INSERT VARIABLE OR RUN PROGRAMMING LOGIC.

            The template engine then replaces variables and instances declared in a template file with actual values at runtime, and convert the template into an HTML file sent to the client.

        MUSTACE
            logic-less templates, it was names mustache because the symbol resembles a mustache.{{}}
            Mustache is a log-less template syntax. It can be used for HTML, config files, source coode -- anything. It works by expanding tags in a template using values provided in a hash or object.

            it is referred to as "logic-less" because there are no if statements, else clauses, or for loops. Instead, there are only tags. Some tags are replaced with a value, some nothing, and others a series of values. 

            mustache.js is an implementation of the mustache template system in JavaScript. It is often considered the base for JavaScript templating. And, since mustache supports various languages, we don't need a separate templating system on the server side. 
                Example: Mustache.render("Hello, {{name}}", { name: "Sherlynn"});
                
            Mustache is a specification for a templating language.

A GUIDE TO FLEXBOX:
    The flexbox layout module aims at providing a more efficient way to lay out, align and distribute space among items in a container, even when their size is unknown and or/ dynamic(thus the word flex).

    The idea behind the flex layout is to give the container the ability to alter its items' width/height (and order) to best fill the available space. A flex item expands items to fill available free space or shrinks them to prevent overflow. 


    OVERVIEW:
        main axis - the main axis of a flex container is the primary axis along which flex items are laid out. IT IS NOT ALWAYS HORIZONTAL, depends on flex-direction.

        main-start|main-end -- the flex items are placed within the container starting from the main-start and going to main-end. 

        main size - a flex item's width or height, whichever is in the main dimension, is the item's main size. the flex item's main size property is either the 'width' or 'height' property, whichever is in the main dimension. 

        cross axis - the axis perpendicular to the main axis is called the cross axis. its direction depends on main axis direction. 



        DEFINITIONS:
            display - this defines a flex container; inline or bloock depending on the given value. It enables a flex context for all its direct children.

            flex-direction - establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is a single-direction layout concept. Think of items as primarily laying out either in horizontal rows or vertical columns.
                Example: flex-direction: row | row-reverse | column | column-reverse;
                    row(default): left to right

            flex-wrap - by default, flex items will all try fit onto one line. You can change that and allow the items to wrap as needed with this property. 

            order - determines the order the items are laid out. //order:<integer>

            flex-grow - allows you to grow a flex item, takes a number 1:1
            flex-shrink - follows flex-grow

            flex-basis - defines the default size of an element before the remaining space is distributed. It can be a length of anything. The auto keyword says look at my width and height. example: flex-basis: 20% | auto;

            flex - shorthand for flex-grow, flex-shrink and flex-basis combined. The second and third paramters flex-shrink and flex-basis are optional. The default is 0 1 auto.

            justify-content - flex-start, flex-end, center, space-between, space-around, space-evenly

            align-self - allows u to take a flex item out of flow 

            align-items - flex-start, flex-end, center, stretch, baseline

            align-content - same as above