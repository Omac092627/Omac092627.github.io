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