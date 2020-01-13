# Inheritance in CSS


Inheritance order: 

__!important > inline styles > id declarations > class declarations__

However, the order of the class declarations in the \<style\> section are also is important. The second declaration will always take precedence over the first. 



```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  #orange-text {
    color: orange;
  }
  .pink-text {
    color: pink !important;
  }
  .blue-text {
    color: blue;
  }
</style>

<h1 id="orange-text" class="pink-text blue-text" style="color: white">Hello World!</h1>
```

## Result

<img src="../pics/3_inheritance.png" alt="alt text" width="400"> 