# CSS flexbox

1. Placing the CSS property __display: flex;__ on an element allows you to use other flex properties to build a responsive page. Adding __display: flex;__ to an element turns it into a __flex container__. This makes it possible to align any children of that element into rows or columns. You do this by adding the __flex-direction__ property to the parent item and setting it to _row_ or _column_. Creating a row will align the children horizontally, and creating a column will align the children vertically.

Other options for __flex-direction__ are _row-reverse_ and _column-reverse_.

_Note_: the default value for the __flex-direction__ property is row.

```html
<style>
  body {
    font-family: Arial, sans-serif;
  }
  header, footer {
    display: flex;
    flex-direction: row;
  }
  header .profile-thumbnail {
    width: 50px;
    height: 50px;
    border-radius: 4px;
  }
  header .profile-name {
    display: flex;
    flex-direction: column;
    margin-left: 10px;
  }
  header .follow-btn {
    display: flex;
    margin: 0 0 0 auto;
  }
  header .follow-btn button {
    border: 0;
    border-radius: 3px;
    padding: 5px;
  }
  header h3, header h4 {
    display: flex;
    margin: 0;
  }
  #inner p {
    margin-bottom: 10px;
    font-size: 20px;
  }
  #inner hr {
    margin: 20px 0;
    border-style: solid;
    opacity: 0.1;
  }
  footer .stats {
    display: flex;
    font-size: 15px;
  }
  footer .stats strong {
    font-size: 18px;
  }
  footer .stats .likes {
    margin-left: 10px;
  }
  footer .cta {
    margin-left: auto;
  }
  footer .cta button {
    border: 0;
    background: transparent;
  }
</style>
<header>
  <img src="https://freecodecamp.s3.amazonaws.com/quincy-twitter-photo.jpg" alt="Quincy Larson's profile picture" class="profile-thumbnail">
  <div class="profile-name">
    <h3>Quincy Larson</h3>
    <h4>@ossia</h4>
  </div>
  <div class="follow-btn">
    <button>Follow</button>
  </div>
</header>
<div id="inner">
  <p>I meet so many people who are in search of that one trick that will help them work smart. Even if you work smart, you still have to work hard.</p>
  <span class="date">1:32 PM - 12 Jan 2018</span>
  <hr>
</div>
<footer>
  <div class="stats">
    <div class="Retweets">
      <strong>107</strong> Retweets
    </div>
    <div class="likes">
      <strong>431</strong> Likes
    </div>
  </div>
  <div class="cta">
    <button class="share-btn">Share</button>
    <button class="retweet-btn">Retweet</button>
    <button class="like-btn">Like</button>
  </div>
</footer>
```

<img src="../pics/9_tweet.png" alt="alt text" width="250">

2. Sometimes the flex items within a flex container do not fill all the space in the container. It is common to want to tell CSS how to align and space out the flex items a certain way. Fortunately, the __justify-content__ property has several options to do this. But first, there is some important terminology to understand before reviewing those options.

Here is a useful image showing a row to illustrate the concepts below:

![flexbox](https://www.w3.org/TR/css-flexbox-1/images/flex-direction-terms.svg)

Recall that setting a flex container as a row places the flex items side-by-side from left-to-right. A flex container set as a column places the flex items in a vertical stack from top-to-bottom. For each, the direction the flex items are arranged is called the main axis. For a row, this is a horizontal line that cuts through each item. And for a column, the main axis is a vertical line through the items.

There are several options for how to space the flex items along the line that is the main axis. One of the most commonly used is __justify-content: center;__ (aligns all the flex items to the center inside the flex container). Others options include:

__flex-start__ aligns items to the start of the flex container. For a row, this pushes the items to the left of the container. For a column, this pushes the items to the top of the container.

__flex-end__ aligns items to the end of the flex container. For a row, this pushes the items to the right of the container. For a column, this pushes the items to the bottom of the container.

__space-between__ aligns items to the center of the main axis, with extra space placed between the items. The first and last items are pushed to the very edge of the flex container. For example, in a row the first item is against the left side of the container, the last item is against the right side of the container, then the other items between them are spaced evenly.

__space-around__ similar to space-between but the first and last items are not locked to the edges of the container, the space is distributed around all the items.


3. The __align-items__ property is similar to __justify-content__. Recall that the __justify-content__ property aligned flex items along the main axis. For rows, the main axis is a horizontal line and for columns it is a vertical line.

Flex containers also have a _cross axis_ which is the opposite of the main axis. For rows, the cross axis is vertical and for columns, the cross axis is horizontal.

CSS offers the __align-items__ property to align flex items along the _cross axis_. For a row, it tells CSS how to push the items in the entire row up or down within the container. And for a column, how to push all the items left or right within the container.

The different values available for __align-items__ include:

__flex-start__ aligns items to the start of the flex container. For rows, this aligns items to the top of the container. For columns, this aligns items to the left of the container.

__flex-end__ aligns items to the end of the flex container. For rows, this aligns items to the bottom of the container. For columns, this aligns items to the right of the container.

__center__ align items to the center. For rows, this vertically aligns items (equal space above and below the items). For columns, this horizontally aligns them (equal space to the left and right of the items).

__stretch__ stretch the items to fill the flex container. For example, rows items are stretched to fill the flex container top-to-bottom.

__baseline__ align items to their baselines. Baseline is a text concept, think of it as the line that the letters sit on.


```html
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 500px;
    align-items: center;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 200px;
    font-size: 24px;
  }

  #box-2 {
    background-color: orangered;
    width: 200px;
    font-size: 18px;
  }
</style>

<div id="box-container">
  <div id="box-1"><p>Hello</p></div>
  <div id="box-2"><p>Goodbye</p></div>
</div>
```

<img src="../pics/9_boxes.png" alt="alt text" width="250">


4. CSS flexbox has a feature to split a flex item into multiple rows (or columns). By default, a flex container will fit all flex items together. For example, a row will all be on one line.

However, using the __flex-wrap__ property, it tells CSS to wrap items. This means extra items move into a new row or column. The break point of where the wrapping happens depends on the size of the items and the size of the container.

CSS also has options for the direction of the wrap:

__nowrap__ this is the default setting, and does not wrap items.

__wrap__ wraps items from left-to-right if they are in a row, or top-to-bottom if they are in a column.

__wrap-reverse__ wraps items from bottom-to-top if they are in a row, or right-to-left if they are in a column.

```html
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 100%;
    flex-wrap: wrap;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 25%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 25%;
    height: 50%;
  }
  #box-3 {
    background-color: violet;
    width: 25%;
    height: 50%;
  }
  #box-4 {
    background-color: yellow;
    width: 25%;
    height: 50%;
  }
  #box-5 {
    background-color: green;
    width: 25%;
    height: 50%;
  }
  #box-6 {
    background-color: black;
    width: 25%;
    height: 50%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
  <div id="box-3"></div>
  <div id="box-4"></div>
  <div id="box-5"></div>
  <div id="box-6"></div>
</div>
```

<img src="../pics/9_wrap.png" alt="alt text" width="250">


5. So far, all the discussed properties apply to the __flex container__ (the parent of the flex items). However, there are several useful properties for the flex items.

The first is the __flex-shrink__ property. When it's used, it allows an item to shrink if the flex container is too small. Items shrink when the width of the parent container is smaller than the combined widths of all the flex items within it.

The __flex-shrink__ property takes numbers as values. The higher the number, the more it will shrink compared to the other items in the container. For example, if one item has a __flex-shrink__ value of 1 and the other has a __flex-shrink__ value of 3, the one with the value of 3 will shrink three times as much as the other.

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 100%;
    height: 200px;
    flex-shrink: 1;
  }

  #box-2 {
    background-color: orangered;
    width: 100%;
    height: 200px;
    flex-shrink: 2;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

<img src="../pics/9_shrink.png" alt="alt text" width="250">


6. The opposite of __flex-shrink__ is the __flex-grow__ property. Recall that __flex-shrink__ controls the size of the items when the container shrinks. The __flex-grow__ property controls the size of items when the parent container expands. If one item has a __flex-grow__ value of 1 and the other has a __flex-grow__ value of 3, the one with the value of 3 will grow three times as much as the other.

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-grow: 1;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    flex-grow: 2;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

<img src="../pics/9_grow.png" alt="alt text" width="250">


7. The __flex-basis__ property specifies the initial size of the item before CSS makes adjustments with __flex-shrink__ or __flex-grow__. The units used by the __flex-basis__ property are the same as other size properties (px, em, %, etc.). The value auto sizes items based on the content.

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-basis: 10em;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    flex-basis: 20em;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

<img src="../pics/9_basis.png" alt="alt text" width="250">


8. There is a shortcut available to set several flex properties at once. The __flex-grow__, __flex-shrink__, and __flex-basis__ properties can all be set together by using the __flex__ property.

For example, __flex: 1 0 10px;__ will set the item to __flex-grow: 1;, flex-shrink: 0;, and flex-basis: 10px;__

The default property settings are __flex: 0 1 auto;__


9. The __order__ property is used to tell CSS the order of how flex items appear in the flex container. By default, items will appear in the same order they come in the source HTML. The property takes numbers as values, and negative numbers can be used.

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    order: 2;
    height: 200px;
    width: 200px;
  }

  #box-2 {
    background-color: orangered;
    order: 1;
    height: 200px;
    width: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

<img src="../pics/9_order.png" alt="alt text" width="250">


10. The final property for flex items is __align-self__. This property allows you to adjust each item's alignment individually, instead of setting them all at once. This is useful since other common adjustment techniques using the CSS properties float, clear, and vertical-align do not work on flex items.

__align-self__ accepts the same values as align-items and will override any value set by the align-items property.

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    align-self: center;
    height: 200px;
    width: 200px;
  }

  #box-2 {
    background-color: orangered;
    align-self: flex-end;
    height: 200px;
    width: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

<img src="../pics/9_allign_self.png" alt="alt text" width="250">
