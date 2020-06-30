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