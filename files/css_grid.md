# CSS grid

1. Turn any HTML element into a grid container by setting its __display__ property to _grid_. This gives you the ability to use all the other properties associated with CSS grid.

_Note_: in CSS grid, the parent element is referred to as the __container__ and its children are called __items__.


2. Simply creating a grid element doesn't get you very far. You need to define the structure of the grid as well. To add some columns to the grid, use the __grid-template-columns__ property on a grid container as demonstrated below:

```html
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```

This will give your grid two columns that are 50px wide each. The number of parameters given to the __grid-template-columns__ property indicates the number of columns in the grid, and the value of each parameter indicates the width of each column.


3. That grid will set the number of rows automatically. To adjust the rows manually, use the __grid-template-rows__ property in the same way you used __grid-template-columns__ in previous challenge.


4. You can use absolute and relative units like _px_ and _em_ in CSS Grid to define the size of rows and columns. You can use these as well:

__fr__ sets the column or row to a fraction of the available space.

__auto__ sets the column or row to the width or height of its content automatically.

__%__ adjusts the column or row to the percent width of its container.

For example:

__grid-template-columns: auto 50px 10% 2fr 1fr;__

This snippet creates five columns. The first column is as wide as its content, the second column is 50px, the third column is 10% of its container, and for the last two columns; the remaining space is divided into three sections, two are allocated for the fourth column, and one for the fifth.


5. So far in the grids you have created, the columns have all been tight up against each other. Sometimes you want a gap in between the columns. To add a gap between the columns, use the __grid-column-gap__ property like this:

__grid-column-gap: 10px;__

This creates 10px of empty space between all of our columns.


6. You can add a gap in between the rows of a grid using __grid-row-gap__ in the same way that was shown in the previous section.


7. __grid-gap__ is a shorthand property for __grid-row-gap__ and __grid-column-gap__ that's more convenient to use. If __grid-gap__ has one value, it will create a gap between all rows and columns. However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.


8. Up to this point, all the properties that have been discussed are for grid containers. The __grid-column__ property is the first one for use on the grid items themselves.

The hypothetical horizontal and vertical lines that create the grid are referred to as lines. These lines are numbered starting with 1 at the top left corner of the grid and move right for columns and down for rows, counting upward.


9. Of course, you can make items consume multiple rows just like you can with columns. You define the horizontal lines you want an item to start and stop at using the __grid-row__ property on a grid item.


10. In CSS grid, the content of each item is located in a box which is referred to as a cell. You can align the content's position within its cell horizontally using the __justify-self__ property on a grid item. By default, this property has a value of _stretch_, which will make the content fill the whole width of the cell. This CSS grid property accepts other values as well:

__start__ aligns the content at the left of the cell.

__center__ aligns the content in the center of the cell.

__end__ aligns the content at the right of the cell.

11. Just as you can align an item horizontally, there's a way to align an item vertically as well. To do this, you use the __align-self__ property on an item. This property accepts all of the same values as __justify-self__. 

12. Sometimes you want all the items in your CSS Grid to share the same alignment. You can use the previously learned properties and align them individually, or you can align them all at once horizontally by using __justify-items__ on your grid container. This property can accept all the same values you learned about in the previous two challenges, the difference being that it will move all the items in our grid to the desired alignment.

13. Using the __align-items__ property on a grid container will set the vertical alignment for all the items in our grid.

14. You can group cells of your grid together into an area and give the area a custom name. Do this by using __grid-template-areas__ on the container like this:

```html
grid-template-areas:
  "header header header"
  "advert content content"
  "footer footer footer";
```

The code above merges the top three cells together into an area named header, the bottom three cells into a footer area, and it makes two areas in the middle row: advert and content.

_Note_: every word in the code represents a cell and every pair of quotation marks represent a row.

In addition to custom labels, you can use a period to designate an empty cell in the grid.

15. After creating an areas template for your grid container, as shown in the previous challenge, you can place an item in your custom area by referencing the name you gave it. To do this, you use the __grid-area__ property on an item like this:

__.item1 { grid-area: header; }__

This lets the grid know that you want the _item1_ class to go in the area named header. In this case, the item will use the entire top row because that whole row is named as the header area.

16. The __grid-area__ property can be used in another way. If your grid doesn't have an areas template to reference, you can create an area on the fly for an item to be placed like this:

__item1 { grid-area: 1/1/2/4; }__

This is using the line numbers you learned about earlier to define where the area for this item will be. The numbers in the example above represent these values:

__grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;__

So the item in the example will consume the rows between lines 1 and 2, and the columns between lines 1 and 4.

17. When you used __grid-template-columns__ and __grid-template-rows__ to define the structure of a grid, you entered a value for each row or column you created.

Lets say you want a grid with 100 rows of the same height. It isn't very practical to insert 100 values individually. Fortunately, there's a better way - by using the __repeat__ function to specify the number of times you want your column or row to be repeated, followed by a comma and the value you want to repeat.

Here's an example that would create the 100 row grid, each row at 50px tall.

__grid-template-rows: repeat(100, 50px);__

You can also repeat multiple values with the repeat function, and insert the function amongst other values when defining a grid structure. Here's what I mean:

__grid-template-columns: repeat(2, 1fr 50px) 20px;__

This translates to:

__grid-template-columns: 1fr 50px 1fr 50px 20px;__

_Note_: 1fr 50px is repeated twice followed by 20px. 


18. There's another built-in function to use with __grid-template-columns__ and __grid-template-rows__ called __minmax__. It's used to limit the size of items when the grid container changes size. To do this you need to specify the acceptable size range for your item. Here is an example:

__grid-template-columns: 100px minmax(50px, 200px);__

In the code above, __grid-template-columns__ is set to create two columns; the first is 100px wide, and the second has the minimum width of 50px and the maximum width of 200px.

19. The __repeat__ function comes with an option called __auto-fill__. This allows you to automatically insert as many rows or columns of your desired size as possible depending on the size of the container. You can create flexible layouts when combining __auto-fill__ with __minmax__:

__repeat(auto-fill, minmax(60px, 1fr));__

When the container changes size, this setup keeps inserting 60px columns and stretching them until it can insert another one.

_Note_: if your container can't fit all your items on one row, it will move them down to a new one.

20. __auto-fit__ works almost identically to __auto-fill__. The only difference is that when the container's size exceeds the size of all the items combined, __auto-fill__ keeps inserting empty rows or columns and pushes your items to the side, while __auto-fit__ collapses those empty rows or columns and stretches your items to fit the size of the container.

_Note_: if your container can't fit all your items on one row, it will move them down to a new one.

21. Turning an element into a grid only affects the behavior of its direct descendants. So by turning a direct descendant into a grid, you have a grid within a grid. For example, by setting the __display__ and __grid-template-columns__ properties of the element with the item3 class, you create a grid within your grid.


## Sample code

```html
<style>
  .item1{background:LightSkyBlue;}
  .item2{background:LightSalmon;}
  .item3{background:PaleTurquoise;}
  .item4{background:LightPink;}
  .item5{background:PaleGreen;}
  
  .container {
    font-size: 40px;
    min-height: 100px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: repeat( auto-fill, minmax(60px, 1fr));
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
  
  .container2 {
    font-size: 40px;
    min-height: 100px;
    width: 100%;
    background: Silver;
    display: grid;    
    grid-template-columns: repeat( auto-fit, minmax(60px, 1fr));
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
</style>
  
<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
<div class="container2">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```