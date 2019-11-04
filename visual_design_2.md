# Visual design 2


## Pseudo-class

A pseudo-class is a keyword that can be added to selectors, in order to select a specific state of the element. For example, the styling of an anchor tag can be changed for its hover state using the __:hover pseudo-class__ selector. Here's the CSS to change the color of the anchor tag during its hover state:

```html
<style>
  a {
    color: #000;
  }
  
  a:hover {
  color: blue;
}

</style>

<a href="http://freecatphotoapp.com/" target="_blank">CatPhotoApp</a>
```

## Positioning

1. CSS treats each HTML element as its own box, which is usually referred to as the CSS Box Model. Block-level items automatically start on a new line (think headings, paragraphs, and divs) while inline items sit within surrounding content (like images or spans). The default layout of elements in this way is called the normal flow of a document, but CSS offers the __position__ property to override it.

2. When the position of an element is set to relative, it allows you to specify how CSS should move it relative to its current position in the normal flow of the page. It pairs with the CSS offset properties of left or right, and top or bottom. These say how many pixels, percentages, or ems to move the item away from where it is normally positioned. The following example moves the paragraph 10 pixels away from the bottom:

```html
p {
  position: relative;
  bottom: 10px;
}
```

Changing an element's position to relative does not remove it from the normal flow - other elements around it still behave as if that item were in its default position.

```html
<head>
<style>
  h2 {
    position: relative;
    left: 15px;
    bottom: 10px;
    
  }
</style>
</head>
<body>
  <h1>On Being Well-Positioned</h1>
  <h2>Move me!</h2>
  <p>I still think the h2 is where it normally sits.</p>
</body>
```

3. Positioning gives you a lot of flexibility and power over the visual layout of a page. It's good to remember that no matter the position of elements, the underlying HTML markup should be organized and make sense when read from top to bottom. This is how users with visual impairments (who rely on assistive devices like screen readers) access your content.


4. The next option for the CSS position property is absolute, which locks the element in place relative to its parent container. Unlike the relative position, this removes the element from the normal flow of the document, so surrounding items ignore it. The CSS __offset__ properties (top or bottom and left or right) are used to adjust the position.

One nuance with absolute positioning is that it will be locked relative to its closest positioned ancestor. If you forget to add a position rule to the parent item, (this is typically done using __position: relative;__), the browser will keep looking up the chain and ultimately default to the body tag.

```html
<style>
  #searchbar {   
    position: absolute;
    top: 50px;
    right: 50px;
    
  }
  section {
    position: relative;
  }
</style>

<body>
  <h1>Welcome!</h1>
  <section>
    <form id="searchbar">
      <label for="search">Search:</label>
      <input type="search" id="search" name="search">
      <input type="submit" name="submit" value="Go!">
    </form>
  </section>
</body>
```

5. The next layout scheme that CSS offers is the fixed position, which is a type of absolute positioning that locks an element relative to the browser window. Similar to absolute positioning, it's used with the CSS offset properties and also removes the element from the normal flow of the document. Other items no longer "realize" where it is positioned, which may require some layout adjustments elsewhere.

One key difference between the fixed and absolute positions is that an element with a fixed position won't move when the user scrolls.

```html
<style>
  #navbar {
    position: fixed;
    top: 0px;
    left: 0px;
    width: 100%;
    background-color: #767676;
  }
  nav ul {
    margin: 0px;
    padding: 5px 0px 5px 30px;
  }
  nav li {
    display: inline;
    margin-right: 20px;
  }
  a {
    text-decoration: none;
  }
</style>

<body>
  <header>
    <h1>Welcome!</h1>
    <nav id="navbar">
      <ul>
        <li><a href="">Home</a></li>
        <li><a href="">Contact</a></li>
      </ul>
    </nav>
  </header>
  <p>I shift up when the #navbar is fixed to the browser window.</p>
</body>
```

6. The next positioning tool does not actually use position, but sets the __float__ property of an element. Floating elements are removed from the normal flow of a document and pushed to either the left or right of their containing parent element. It's commonly used with the __width__ property to specify how much horizontal space the floated element requires.

```html
<head>
  <style>
  #left {
    float: left;
    width: 50%;
  }
  #right {
    float: right;
    width: 40%;
  }
  aside, section {
    padding: 2px;
    background-color: #ccc;
  }
  </style>
</head>
<body>
  <header>
    <h1>Welcome!</h1>
  </header>
  <section id="left">
    <h2>Content</h2>
    <p>Good stuff</p>
  </section>
  <aside id="right">
    <h2>Sidebar</h2>
    <p>Links</p>
  </aside>
</body>
```

7. When elements are positioned to overlap, the element coming later in the HTML markup will, by default, appear on the top of the other elements. However, the __z-index__ property can specify the order of how elements are stacked on top of one another. It must be an integer (i.e. a whole number and not a decimal), and higher values for the __z-index__ property of an element move it higher in the stack than those with lower values.

```html
<style>
  div {
    width: 60%;
    height: 200px;
    margin-top: 20px;
  }
  
  .first {
    background-color: red;
    position: absolute;
    z-index: 2;
  }
  .second {
    background-color: blue;
    position: absolute;
    left: 40px;
    top: 50px;
    z-index: 1;
  }
</style>

<div class="first"></div>
<div class="second"></div>
```

8. Another positioning technique is to center a block element horizontally. One way to do this is to set its margin to a value of auto. This method works for images, too. Images are inline elements by default, but can be changed to block elements when you set the display property to block.

```html
<style>
  div {
    background-color: blue;
    height: 100px;
    width: 100px;
    margin: auto;
  }
</style>
<div></div>
```

