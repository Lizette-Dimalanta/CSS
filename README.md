# CSS Basics

Wednesday, 15 August 2022.

# Contents

1. __Notes__
2. __What is CSS?__
3. __Anatomy of a CSS Rule__
4. __Style Tag__
5. __CSS Selectors__
6. __Absolute vs. Relative Units__
7. __Inline, Internal and External StyleSheets__
8. __Cascading Specificity__

# Notes

- __wrt__ = with reference to
- __Kebab Case__: this`-`is`-`kebab`-`case
- __Snake Case:__ this`_`is`_`snake`_`case
- __Camel Case:__ this`I`s`C`amel`C`ase
- __Pascal Case:__ `T`his`I`s`P`ascal`C`ase

# What is CSS?

- __Cascading-Style-Sheet__
- Describes the style of a HTML document.
- __Stylesheet__: Helps web developers separate the _style_ from _content_.
- Style of an element can be defined once and applied everywhere.
- __Cascading__ implies the latest style overrides the previous definition.

# Anatomy of a CSS Rule

![Anatomy of a CSS Rule](https://learnwebcode.com/wp-content/uploads/2010/02/anatomy-of-a-css-rule.gif)

# Style Tag

`<style></style>`

CSS Syntax:

``` html
<!DOCTYPE html>
<html>
    <head>
        <title>Text</title>
        <style>
            [element]{
                property: value;
            }
        </style>
    </head>
    <body>
        <h1>Text</h1>
    </body>
</html>
```

# CSS Selectors

- How we apply style to different HTML elements.
  
    __*More Information*__:

    [CSS Selectors - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)

    [CSS Selector Reference - W3Schools](https://www.w3schools.com/cssref/css_selectors.asp)
- Types of selectors:
  - __Type Selector:__ `h1`, `p`, `img`, `input`
    - Selects all elements that have a given node name
  - __Class Selector:__ `.class`
    - Selects all elements that have a given class attribute.
    - Multiple elements can have the same class attribute
  
        ``` html
                <body>
                    <h2 class="sub-title">Sub Heading 1</h2>
                    <h2 class="sub-title">Sub Heading 2</h2>
                    <h2 class="sub-title">Sub Heading 3</h2>
                </body>
                <style>
                    .sub-title {
                        color:purple;
                        text-align:center;
                        font-size:30px;
                    }
                </style>
        ```

  - __ID Selector:__ `#id`
    - Selects all elements that have a given ID attribute.
    - Can only be applied to one element per page.
  
        ``` html
        <body>
            <h1 id="title">Title</h1>
        </body>
        <style>
            #title{
                color:blue;
                text-align:center;
                font-size:60px;
                font-weight:bold;
            }
        </style>
        ```

  - __Pseudo Classes:__
    - Defines special state of an element.
    - eg. Hovering over a link/mouse over button.
  
        ```html
        <body>
            <h1> Pseudo Class </h1>
        </body>
        <style>
            /*
            selector:pseudo-class{
            property:value;
            } */
            h1:hover{
                color: green;
            }
        </style>
        ```

        __*More Information*__: [Pseudo Classes - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

# Absolute vs. Relative Units

- ### __Absolute Unit:__ Refers to a __*fixed*__ size.
  
  - Not recommended - Responsive resizing not supported
  
  - `px`
  - `cm`
  - `mm`
  
- ### __Relative Unit:__ Responsive to parent element/screen size.
  
  - `%`: width (relative to screen size)
  - `rem`: font-size/padding
  - `em`: font-size (relative to parent container)
  - `vw`
  - `vh`

__*More Information*__: [CSS Units - W3Schools](https://www.w3schools.com/cssref/css_units.asp)

# Inline, Internal and External StyleSheets

__Inline Styling:__ Style an element **_inline_** with the HTML tag.

`<h1 style="color:red; font-size:70px;">Inline Style</h1>`

- Least effective for maintaining large code.

__Internal Style Sheet:__ Style elements in the __*same HTML document*__, requires `<style></style>` tag.

__External Style Sheet:__ Style elements in a __*separate CSS file*__ and links to HTML document.

- Most effective for maintaining large code.

### Linking to external stylesheet:

`<link rel="stylesheet" href="css/style.css">`

# Cascading Specificity

- Calculates highest priority to inline
- Assigns a value system to the different types of selectors.
- A common way of calculating specificity:
  1. __`<Inline Style>`:__ 1000 points
  2. __`#ID`__: 100 points
  3. __`.Class` & Pseudo Class:__ : 10 points
  4. __Element__ `<p>`: 1 point
