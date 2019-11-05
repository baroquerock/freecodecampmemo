# Accessibility

1. It's likely you've seen an __alt__ attribute on an __img__ tag. __Alt__ text describes the content of the image and provides a text alternative. This helps in case the image fails to load or can't be seen by a user. It's also used by search engines to understand what an image contains to include it in search results. Here's an example:

```html
<img src="importantLogo.jpeg" alt="Company logo">
```

People with visual impairments rely on screen readers to convert web content to an audio interface. They won't get information if it's only presented visually. For images, screen readers can access the __alt__ attribute and read its contents to deliver key information. Good __alt__ text is short but descriptive, and meant to briefly convey the meaning of the image. You should always include an alt attribute on your image. Per HTML5 specification, this is now considered mandatory.

```html
<img src="importantLogo.jpeg" alt="Company logo">
```

2. Sometimes images are grouped with a caption already describing them, or are used for decoration only. In these cases alt text may seem redundant or unnecessary. In situations when an image is already explained with text content, or does not add meaning to a page, the img still needs an alt attribute, but it can be set to an empty string. Here's an example:

```html
<img src="visualDecoration.jpeg" alt="">
```

Background images usually fall under the 'decorative' label as well. However, they are typically applied with CSS rules, and therefore not part of the markup screen readers process.

For images with a caption, you may still want to include alt text, since it helps search engines catalog the content of the image.


3. Headings (__h1__ through __h6__ elements) are workhorse tags that help provide structure and labeling to your content. Screen readers can be set to read only the headings on a page so the user gets a summary. This means it is important for the heading tags in your markup to have semantic meaning and relate to each other, not be picked merely for their size values. Semantic meaning means that the tag you use around content indicates the type of information it contains.

If you were writing a paper with an introduction, a body, and a conclusion, it wouldn't make much sense to put the conclusion as a subsection of the body in your outline. It should be its own section. Similarly, the heading tags in a webpage need to go in order and indicate the hierarchical relationships of your content.

Headings with equal (or higher) rank start new implied sections, headings with lower rank start subsections of the previous one. As an example, a page with an __h2__ element followed by several subsections labeled with __h4__ tags would confuse a screen reader user. With six choices, it's tempting to use a tag because it looks better in a browser, but you can use CSS to edit the relative sizing.

One final point, each page should always have one (and only one) __h1__ element, which is the main subject of your content. This and the other headings are used in part by search engines to understand the topic of the page.


4. HTML5 introduced a number of new elements that give developers more options while also incorporating accessibility features. These tags include __main__, __header__, __footer__, __nav__, __article__, and __section__, among others.

By default, a browser renders these elements similarly to the humble __div__. However, using them where appropriate gives additional meaning in your markup. The tag name alone can indicate the type of information it contains, which adds semantic meaning to that content. Assistive technologies can access this information to provide better page summary or navigation options to their users.

The main element is used to wrap (you guessed it) the __main__ content, and there should be only one per page. It's meant to surround the information that's related to the central topic of your page. It's not meant to include items that repeat across pages, like navigation links or banners.

The __main__ tag also has an embedded landmark feature that assistive technology can use to quickly navigate to the main content. If you've ever seen a "Jump to Main Content" link at the top of a page, using a main tag automatically gives assistive devices that functionality.

5. __Article__ is another one of the new HTML5 elements that adds semantic meaning to your markup. Article is a sectioning element, and is used to wrap independent, self-contained content. The tag works well with blog entries, forum posts, or news articles.

Determining whether content can stand alone is usually a judgement call, but there are a couple simple tests you can use. Ask yourself if you removed all surrounding context, would that content still make sense? Similarly for text, would the content hold up if it were in an RSS feed? Remember that folks using assistive technologies rely on organized, semantically meaningful markup to better understand your work.

_A note about section and div:_ the __section__ element is also new with HTML5, and has a slightly different semantic meaning than article. An article is for standalone content, and a section is for grouping thematically related content. They can be used within each other, as needed. For example, if a book is the article, then each chapter is a section. When there's no relationship between groups of content, then use a div.

__\<div\>__ - groups content

__\<section\>__ - groups related content

__\<article\>__ - groups independent, self-contained content

6. The next HTML5 element that adds semantic meaning and improves accessibility is the __header__ tag. It's used to wrap introductory information or navigation links for its parent tag, and works well around content that's repeated at the top on multiple pages. __Header__ shares the embedded landmark feature you saw with main, allowing assistive technologies to quickly navigate to that content.

_Note_: __header__ is meant for use in the __body__ tag of your HTML document. This is different than the __head__ element, which contains the page's title, meta information, etc.

7. The __nav__ element is another HTML5 item with the embedded landmark feature for easy screen reader navigation. This tag is meant to wrap around the main navigation links in your page. If there are repeated site links at the bottom of the page, it isn't necessary to markup those with a __nav__ tag as well. Using a __footer__ is sufficient.

8. Similar to __header__ and __nav__, the __footer__ element has a built-in landmark feature that allows assistive devices to quickly navigate to it. It's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page.

9. HTML5's __audio__ element gives semantic meaning when it wraps sound or audio stream content in your markup. Audio content also needs a text alternative to be accessible to people who are deaf or hard of hearing. This can be done with nearby text on the page or a link to a transcript.

The __audio__ tag supports the controls attribute. This shows the browser default play, pause, and other controls, and supports keyboard functionality. This is a boolean attribute, meaning it doesn't need a value, its presence on the tag turns the setting on.

Here's an example:

```html
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg" />
  <source src="audio/meow.ogg" type="audio/ogg" />
</audio>
```

_Note_: multimedia content usually has both visual and auditory components. It needs synchronized captions and a transcript so users with visual and/or auditory impairments can access it. Generally, a web developer is not responsible for creating the captions or transcript, but needs to know to include them.

 
10. HTML5 introduced the __figure__ element, along with the related __figcaption__. Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. This gives a two-fold accessibility boost by both semantically grouping related content, and providing a text alternative that explains the figure.

For data visualizations like charts, the caption can be used to briefly note the trends or conclusions for users with visual impairments. Another challenge covers how to move a table version of the chart's data off-screen (using CSS) for screen reader users.

Here's an example (note that the __figcaption__ goes inside the __figure__ tags and can be combined with other elements):

```html
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
  <br>
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```


11. Improving accessibility with semantic HTML markup applies to using both appropriate tag names as well as attributes. This part covers some important scenarios using attributes in forms.

The __label__ tag wraps the text for a specific form control item, usually the name or label for a choice. This ties meaning to the item and makes the form more readable. The __for__ attribute on a __label__ tag explicitly associates that label with the form control and is used by screen readers.

You learned about radio buttons and their labels in a lesson in the Basic HTML section. In that lesson, we wrapped the radio button input element inside a label element along with the label text in order to make the text clickable. Another way to achieve this is by using the __for__ attribute as explained in this lesson.

The value of the __for__ attribute must be the same as the value of the __id__ attribute of the form control.


12. The next form topic covers accessibility of radio buttons. Each choice is given a label with a __for__ attribute tying to the id of the corresponding item. Since radio buttons often come in a group where the user must choose one, there's a way to semantically show the choices are part of a set.

The __fieldset__ tag surrounds the entire grouping of radio buttons to achieve this. It often uses a __legend__ tag to provide a description for the grouping, which is read by screen readers for each choice in the __fieldset__ element.

The __fieldset__ wrapper and __legend__ tag are not necessary when the choices are self-explanatory, like a gender selection. Using a label with the for attribute for each radio button is sufficient.

Here's an example:

```html
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one">
    <label for="one">Choice One</label><br>
    <input id="two" type="radio" name="items" value="two">
    <label for="two">Choice Two</label><br>
    <input id="three" type="radio" name="items" value="three">
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```

13. Forms often include the __input field__, which can be used to create several different form controls. The __type__ attribute on this element indicates what kind of input will be created.

You may have noticed the __text__ and __submit__ input types previously, and HTML5 introduced an option to specify a __date__ field. Depending on browser support, a date picker shows up in the input field when it's in focus, which makes filling in a form easier for all users.

For older browsers, the type will default to text, so it helps to show users the expected date format in the label or as placeholder text just in case.

Here's an example:

```html
<label for="input1">Enter a date:</label>
<input type="date" id="input1" name="input1">
```

14. Continuing with the date theme, HTML5 also introduced the __time__ element along with a __datetime__ attribute to standardize times. This is an inline element that can wrap a date or time on a page. A valid format of that date is held by the __datetime__ attribute. This is the value accessed by assistive devices. It helps avoid confusion by stating a standardized version of a time, even if it's written in an informal or colloquial manner in the text.

Here's an example:

```html
<p>Master Camper Cat officiated the cage match between Goro and Scorpion <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.</p>
```

15. Have you noticed that all of the applied accessibility challenges so far haven't used any CSS? This is to show the importance of a logical document outline, and using semantically meaningful tags around your content before introducing the visual design aspect.

However, CSS's magic can also improve accessibility on your page when you want to visually hide content meant only for screen readers. This happens when information is in a visual format (like a chart), but screen reader users need an alternative presentation (like a table) to access the data. CSS is used to position the screen reader-only elements off the visual area of the browser window.

Here's an example of the CSS rules that accomplish this:

```html
.sr-only {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  top: auto;
  overflow: hidden;
}
```

_Note_: the following CSS approaches will NOT do the same thing:

__display: none;__ or __visibility: hidden;__ hides content for everyone, including screen reader users

Zero values for pixel sizes, such as __width: 0px; height: 0px;__ removes that element from the flow of your document, meaning screen readers will ignore it.

16. Low contrast between the foreground and background colors can make text difficult to read. Sufficient contrast improves the readability of your content, but what exactly does "sufficient" mean?

The Web Content Accessibility Guidelines (WCAG) recommend at least a 4.5 to 1 contrast ratio for normal text. The ratio is calculated by comparing the relative luminance values of two colors. This ranges from 1:1 for the same color, or no contrast, to 21:1 for white against black, the strongest contrast. There are many contrast checking tools available online that calculate this ratio for you.

17. Color is a large part of visual design, but its use introduces two accessibility issues. First, color alone should not be used as the only way to convey important information because screen reader users won't see it. Second, foreground and background colors need sufficient contrast so colorblind users can distinguish them.

Colorblind users have trouble distinguishing some colors from others - usually in hue but sometimes lightness as well. You may recall the contrast ratio is calculated using the relative luminance (or lightness) values of the foreground and background colors.

In practice, the 4.5:1 ratio can be reached by darkening the darker color and lightening the lighter one with the aid of a color contrast checker. Darker colors on the color wheel are considered to be blues, violets, magentas, and reds, whereas lighter colors are oranges, yellows, greens, and blue-greens.

18. There are various forms of colorblindness. These can range from a reduced sensitivity to a certain wavelength of light to the inability to see color at all. The most common form is a reduced sensitivity to detect greens.

For example, if two similar green colors are the foreground and background color of your content, a colorblind user may not be able to distinguish them. Close colors can be thought of as neighbors on the color wheel, and those combinations should be avoided when conveying important information.

_Note_: some online color picking tools include visual simulations of how colors appear for different types of colorblindness. These are great resources in addition to online contrast checking calculators.


19. Screen reader users have different options for what type of content their device reads. This includes skipping to (or over) landmark elements, jumping to the main content, or getting a page summary from the headings. Another option is to only hear the links available on a page.

Screen readers do this by reading the link text, or what's between the anchor __a__ tag. Having a list of "click here" or "read more" links isn't helpful. Instead, you should use brief but descriptive text within the __a__ tags to provide more meaning for these users.


20. HTML offers the __accesskey__ attribute to specify a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users.

HTML5 allows this attribute to be used on any element, but it's particularly useful when it's used with interactive ones. This includes links, buttons, and form controls.

Here's an example:

```html
<button accesskey="b">Important Button</button>
```

21. The HTML __tabindex__ attribute has three distinct functions relating to an element's keyboard focus. When it's on a tag, it indicates that element can be focused on. The value (an integer that's positive, negative, or zero) determines the behavior.

Certain elements, such as links and form controls, automatically receive keyboard focus when a user tabs through a page. It's in the same order as the elements come in the HTML source markup. This same functionality can be given to other elements, such as div, span, and p, by placing a __tabindex="0"__ attribute on them. Here's an example:

```html
<div tabindex="0">I need keyboard focus!</div>
```

_Note_: a negative __tabindex__ value (typically -1) indicates that an element is focusable, but is not reachable by the keyboard. This method is generally used to bring focus to content programmatically (like when a div used for a pop-up window is activated), and is beyond the scope of these lessons.


22. The __tabindex__ attribute also specifies the exact tab order of elements. This is achieved when the value of the attribute is set to a positive number of 1 or higher.

Setting a __tabindex="1"__ will bring keyboard focus to that element first. Then it cycles through the sequence of specified __tabindex__ values (2, 3, etc.), before moving to default and __tabindex="0"__ items.

It's important to note that when the tab order is set this way, it overrides the default order (which uses the HTML source). This may confuse users who are expecting to start navigation from the top of the page. This technique may be necessary in some circumstances, but in terms of accessibility, take care before applying it.

Here's an example:

```html
<div tabindex="1">I get keyboard focus, and I get it first!</div>

<div tabindex="2">I get keyboard focus, and I get it second!</div>
```