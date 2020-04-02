CSS GRID: 

COMPLETED THE TUTORIAL IN UNDERSTANDING HOW GRID LAYOUT WORKS.

display
Establishes a new grid formatting context for children.

display: grid; 
display: inline-grid; 
display: subgrid;
 
grid-template
Defines the rows and columns of the grid.

grid-template-columns: 12px 12px 12px;
grid-template-rows: 12px 12px 12px; 
grid-template-columns: repeat(3, 12px);
grid-template-rows: repeat(3, auto); 
grid-template-columns: 8px auto 8px;
grid-template-rows: 8px auto 12px; 
grid-template-columns: 22% 22% auto;
grid-template-rows: 22% auto 22%;
 
grid-gap
Specifies the size of column and row gutters.

grid-row-gap: 1px;
grid-column-gap: 9px; 
grid-gap: 1px 9px; 
grid-gap: 6px;
 
justify-items
Aligns content in a grid item along the row axis.

justify-items: start; 
justify-items: end; 
justify-items: center; 
justify-items: stretch; (default)


align-items
Aligns content in a grid item along the column axis.

align-items: start; 
align-items: end; 
align-items: center; 
align-items: stretch; (default)
 
justify-content
Justifies all grid content on row axis when total grid size is smaller than container.

justify-content: start; 
justify-content: end; 
justify-content: center; 
justify-content: stretch; 
justify-content: space-around; 
justify-content: space-between; 
justify-content: space-evenly;
 
align-content
Justifies all grid content on column axis when total grid size is smaller than container.

align-content: start; 
align-content: end; 
align-content: center; 
align-content: stretch; 
align-content: space-around; 
align-content: space-between; 
align-content: space-evenly;
 
grid-auto-flow
Algorithm for automatically placing grid items that aren't explictly placed.

grid-auto-flow: row; 
grid-auto-flow: column; 
grid-auto-flow: dense;
