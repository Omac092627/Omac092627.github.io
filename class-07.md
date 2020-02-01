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