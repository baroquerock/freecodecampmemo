# Responsive Web Design principles

1. __Media Queries__ are a new technique introduced in CSS3 that change the presentation of content based on different _viewport_ sizes. The _viewport_ is a user's visible area of a web page, and is different depending on the device used to access the site.

__Media Queries__ consist of a __media type__, and if that media type matches the type of device the document is displayed on, the styles are applied. You can have as many selectors and styles inside your media query as you want.

Here's an example of a media query that returns the content when the device's width is less than or equal to 100px:

__@media (max-width: 100px) { /* CSS Rules */ }__

and the following media query returns the content when the device's height is more than or equal to 350px:

__@media (min-height: 350px) { /* CSS Rules */ }__

Remember, the CSS inside the media query is applied only if the media type matches that of the device being used.


2. Making images responsive with CSS is actually very simple. Instead of applying an absolute width to an element:

```html
img { width: 720px; }
```

You can use:

```html
img {
  max-width: 100%;
  display: block;
  height: auto;
}
```

The __max-width__ property of 100% scales the image to fit the width of its container, but the image won't stretch wider than its original width. Setting the __display__ property to _block_ changes the image from an inline element (its default), to a block element on its own line. The __height__ property of _auto_ keeps the original aspect ratio of the image.


3. The simplest way to make your images appear "retina" (and optimize them for retina displays) is to define their width and height values as only half of what the original file is.

Here is an example of an image that is only using half of the original height and width:

```html
<style>
  img { height: 250px; width: 250px; }
</style>
<img src="coolPic500x500" alt="A most excellent picture">
```

4. Instead of using _em_ or _px_ to size text, you can use __viewport units__ for responsive typography. __Viewport units__, like percentages, are relative units, but they are based off different items. __Viewport units__ are relative to the viewport dimensions (width or height) of a device, and percentages are relative to the size of the parent container element.

The four different viewport units are:

__vw: 10vw__ would be 10% of the viewport's width

__vh: 3vh__ would be 3% of the viewport's height

__vmin: 70vmin__ would be 70% of the viewport's smaller dimension (height vs. width)

__vmax: 100vmax__ would be 100% of the viewport's bigger dimension (height vs. width)
