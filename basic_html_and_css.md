# Basic HTML and CSS

The <!DOCTYPE ...> tag shows the version of HTML. For HTML5, you use <!DOCTYPE html>.
The ! and uppercase DOCTYPE is important, especially for older browsers. The html is not case sensitive.

Here's an example of a page's layout:

```html
<!DOCTYPE html>
<html>
  <head> </head> (Metadata elements - link, meta, title, style)
  <body> </body> (Content of the page)
</html>
```



```html

<!DOCTYPE html>

<html>

<head>

    <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">

    <style>
        .red-text {
            color: red;
        }
        
        h2 {
            font-family: Lobster, monospace;
        }
        
        p {
            font-size: 16px;
            font-family: monospace;
        }
        
        .thick-green-border {
            border-color: green;
            border-width: 10px;
            border-style: solid;
            border-radius: 50%;
        }
        
        .smaller-image {
            width: 100px;
        }
        
        .silver-background {
            background-color: silver;
        }
        
        #cat-photo-form {
            background-color: green;
        }
        
        [type='checkbox'] {
            margin: 10px 0px 15px 0px;
        }
    </style>

</head>

<body>

    <h2 class="red-text">CatPhotoApp</h2>

    <main>

        <p class="red-text">Click here to view more <a href="#">cat photos</a>.</p>

        <p>
            View more <a href="http://freecatphotoapp.com" target="_blank">cat photos</a>
        </p>

        <a href="#"><img class="smaller-image thick-green-border" src="https://bit.ly/fcc-relaxing-cat" alt="A cute orange cat lying on its back."></a>

        <div class="silver-background">

            <p>Things cats love:</p>
            <ul>
                <li>cat nip</li>
                <li>laser pointers</li>
                <li>lasagna</li>
            </ul>
            <p>Top 3 things cats hate:</p>
            <ol>
                <li>flea treatment</li>
                <li>thunder</li>
                <li>other cats</li>
            </ol>

        </div>

        <form action="/submit-cat-photo" id="cat-photo-form">

            <label for="indoor">
                <input id="indoor" type="radio" name="indoor-outdoor" checked> Indoor</label>
            <label for="outdoor">
                <input id="outdoor" type="radio" name="indoor-outdoor"> Outdoor</label>
            <br>
            <label for="loving">
                <input id="loving" type="checkbox" name="personality" checked> Loving</label>
            <label for="lazy">
                <input id="lazy" type="checkbox" name="personality"> Lazy</label>
            <label for="energetic">
                <input id="energetic" type="checkbox" name="personality"> Energetic</label>
            <br>
            <input type="text" placeholder="cat photo URL" required>
            <button type="submit">Submit</button>

        </form>

    </main>

</body>

</html>
```