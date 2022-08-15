# CSS Basics

Wednesday, 15 August 2022.

# What is CSS?
- __Cascading-Style-Sheet__
- Describes the style of a HTML document.
- __Stylesheet__: Helps web developers separate the _style_ from _content_.
- Style of an element can be defined once and applied everywhere.
- __Cascading__ implies the latest style overrides the previous definition.

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

# CSS Properties

- ### Classes
  - Classes start with `'.'`

# CSS Selectors
- How we apply style to different HTML elements.
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
    - Should be only used for unique/particular attributes.
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

  - __Pseudo Classes:__ Selects elements based on state information
    - eg. Hovering over a link/mouse over button.