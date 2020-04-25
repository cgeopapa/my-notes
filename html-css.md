# HTML
## Import css stylesheet
```html
<link rel="stylesheet" type="text/css" href="filename.css">
```
-----------------------------------------
## Import javascript script
```html
<script src="filename.js"></script>
```
-----------------------------------------
## Body tags
```html
<nav></nav>
<header></header>
<main></main>
<footer></footer>
```
-----------------------------------------
## Image don't forget alt
```html
<img src="filename" alt="logo">
```
# CSS
## Font import
```css
@font-face{
    font-family: fontname;
    src: url(filename.ttf);
}
```
Then use font as normal with the fontname

--------------
## Margin/Padding/Border etc
```css
margin: top right bottom left;
```
----------
## Box Shadow
```css
box-shadow: x y blur color [inset], ...
```
-----
## Flexbox
```css
display: flex;
```
Now this is the parent and we can now manipulate its children. The most important selectors
```css
flex-direction: row | row-reverse | column | column-reverse;
flex-wrap: nowrap | wrap | wrap-reverse;
justify-content: flex-start | flex-end | center | space-between [...];
align-items: stretch | flex-start | flex-end | center | baseline [...];
```
### [Amazing documentation about flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

-----------
## Grid (Flexible Grid)
```css
display: grid;
```
The fr unit (fr = fraction)
```css
grid-template-columns: minmax(0, 4fr) 3fr;
```
This means first column's width will range from 0 to 4/7ths of the page. The second one's will be constantly be 3/7ths. It's 7ths because we have 4fr + 3fr, it tries to split the screen to equal parts and give 4 of them to the first column and 3 to the second.

----------
## Media query
Change elements according screen width
```css
@media only screen and (max-width: 800px){
    ...
}
```
---------
## Remove ul bullets
```css
ul{
    list-style: none;
}
```
-----------
## Horizontal list
```css
li{
    float: left;
}
```