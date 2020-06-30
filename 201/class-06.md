JAVASCRIPT:

  Example:
    Creating an object: literal notation.
              Liter notation is the easiest and mos popular way to create objects.
              The object is the curly braces and their content.
              For example a hotel:
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