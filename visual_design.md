# Visual design 1


## Text

1. Text is often a large part of web content. CSS has several options for how to align it with the __text-align__ property.

__text-align: justify;__ causes all lines of text except the last line to meet the left and right edges of the line box

__text-align: center;__ centers the text

__text-align: right;__ right-aligns the text

__text-align: left;__ (the default) left-aligns the text


2. You can specify the width of an element using the __width__ property in CSS. Values can be given in relative length units (such as em), absolute length units (such as px), or as a percentage of its containing parent element. 

3. You can specify the height of an element using the __height__ property in CSS, similar to the width property. 

4. To make text bold, you can use the __strong__ tag. This is often used to draw attention to text and symbolize that it is important. With the strong tag, the browser applies the CSS of __font-weight: bold;__ to the element.

5. To underline text, you can use the __u__ tag. This is often used to signify that a section of text is important, or something to remember. With the __u__ tag, the browser applies the CSS of __text-decoration: underline;__ to the element.

6. To emphasize text, you can use the __em__ tag. This displays text as italicized, as the browser applies the CSS of __font-style: italic;__ to the element.

7. To strikethrough text, which is when a horizontal line cuts across the characters, you can use the __s__ tag. It shows that a section of text is no longer valid. With the __s__ tag, the browser applies the CSS of __text-decoration: line-through;__ to the element.

8. You can use the __hr__ tag to add a horizontal line across the width of its containing element. This can be used to define a change in topic or to visually separate groups of content. The tag is self closing. 

9. The font size of header tags (__h1__ through __h6__) should generally be larger than the font size of paragraph tags. This makes it easier for the user to visually understand the layout and level of importance of everything on the page. You use the __font-size__ property to adjust the size of the text in an element.

10. The __box-shadow__ property applies one or more shadows to an element. The __box-shadow__ property takes values for _offset-x_ (how far to push the shadow horizontally from the element), _offset-y_ (how far to push the shadow vertically from the element), _blur-radius_, _spread-radius_ and a color value, in that order. The _blur-radius_ and _spread-radius_ values are optional.

11. The __opacity__ property in CSS is used to adjust the opacity, or conversely, the transparency for an item.

12. The __text-transform__ property in CSS is used to change the appearance of text. It's a convenient way to make sure text on a webpage appears consistently, without having to change the text content of the actual HTML elements.

13. The __font-weight__ property sets how thick or thin characters are in a section of text.

14. CSS offers the __line-height__ property to change the height of each line in a block of text. As the name suggests, it changes the amount of vertical space that each line of text gets.

## Sample code

```html
<style>
  
    h4 {
        text-align: center;
        background-color: rgba(45, 45, 45, 0.1);
        padding: 10px;
        font-size: 27px;
        text-transform: uppercase;
    }
    
    p {
        text-align: justify;
    }
    
    .links {
        text-align: left;
        color: black;
        opacity: 0.7;
    }
    
    #thumbnail {
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);
    }
    
    .fullCard {
        width: 245px;
        border: 1px solid #ccc;
        border-radius: 5px;
        margin: 10px 5px;
        padding: 4px;
    }
    
    .cardContent {
        padding: 10px;
    }
    
    .cardText {
        margin-bottom: 30px;
    }
  
</style>

<div class="fullCard" id="thumbnail">
  
    <div class="cardContent">
        <div class="cardText">
            <h4>Alphabet</h4>
            <hr>
            <p><em>Google was founded by Larry Page and Sergey Brin while they were <u>Ph.D. students</u> at <strong>Stanford University</strong>.</em></p>
        </div>
        <div class="cardLinks">
            <a href="https://en.wikipedia.org/wiki/Larry_Page" target="_blank" class="links">Larry Page</a>
            <br>
            <br>
            <a href="https://en.wikipedia.org/wiki/Sergey_Brin" target="_blank" class="links">Sergey Brin</a>
        </div>
    </div>
  
</div>
```