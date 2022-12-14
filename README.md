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

__*More Information*__: 

[CSS Introduction - W3Schools](https://www.w3schools.com/css/css_intro.asp)

[CSS: Cascading Style Sheets - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS)

# Anatomy of a CSS Ruleset

![Anatomy of a CSS Rule](https://static.au.edusercontent.com/files/8fC7Q2nH6xjwkJeYwnJzfVwq)

## Definitions:

- __Ruleset__: `p{color: red;}`
  - The whole structure.
- __Selector__: `<p>`
  - The left hand side of the ruleset.
  - Determines which elements will be styled.
- __Property__: `color:`
  - Which property of the selected element you want to change.
- __Property Value__: `red;`
  - Choose from possible values for given property.
- __Declaration__: `color: red;`
  - Combination of property and property value.

# Style Tag

`<style></style>`

CSS Syntax:

``` html
<!DOCTYPE html>
<html>
  <style>
    p {
      color: green;
      text-decoration: underline;
      font-size: 20px;
    }
  </style>
  <p>I'm a styled paragraph</p>
  <p>I'm another styled paragraph</p>
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
    - A way to style elements in a specific state, such as being hovered over.

    `.selector:psuedo-class {
  attribute: property;
}`
  
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
  
  - `%`: Relative to screen size/parent element.
  - `rem`: `font-size`/`padding`
  - `em`: font-size _(relative to parent container)_
  - `vw`: Relative to viewport height _(eg. a landing page that takes up the entire screen of whatever device it is viewed on)_
  - `vh`: Relative to `font-size` of root element.

__*More Information*__: 

[CSS Values and Units - MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

[CSS Units - W3Schools](https://www.w3schools.com/cssref/css_units.asp)

[A Guide on When to Use Which Unit Values](https://elementor.com/help/whats-the-difference-between-px-em-rem-vw-and-vh/#:~:text=EM%20is%20relative%20to%20the,parent%20size%20is%2C%20use%20REM.)

# Inline, Internal and External StyleSheets

__Inline Styling:__ Style an element **_inline_** with the HTML tag.

`<p style="color: red">Inline styling is handy</p>`

- We can keep adding key value pairs in the style attribute, as long as we separate them with a semicolon `';'`.
- Least effective for maintaining large code.

__Internal Style Sheet:__ Style elements in the __*same HTML document*__, requires `<style></style>` tag.

__External Style Sheet:__ Style elements in a __*separate CSS file*__ and links to HTML document.

- Most effective for maintaining large code.

### Linking to external stylesheet:

`<link rel="stylesheet" href="css/style.css"/>`

# Cascading Specificity

- Calculates highest priority to inline
- Assigns a value system to the different types of selectors.
- A common way of calculating specificity:
  1. __`<Inline Style>`:__ 1000 points
  2. __`#ID`__: 100 points

        ![ID-level Specificity](https://static.au.edusercontent.com/files/SSQKw7dsf9nZTLHYwgGMvHpT)

  3. __`.Class` & Pseudo Class:__ : 10 points

        ![Class-level Specificity](https://static.au.edusercontent.com/files/gHbQs48btnDuABdFI8ta1Bdj)

  4. __Element__ `<p>`: 1 point

        ![Element-level Specificity](https://static.au.edusercontent.com/files/CK21lEi9H0NB1BsN6lZZs2mC)
