#FOUNDATIONS session 4

##Basilica

Examine code with regards to the [recipe schema](https://schema.org/Recipe) at [schema.org](http://schema.org/docs/gs.html). Here is an [example](http://www.foodnetwork.com/recipes/food-network-kitchens/basil-pesto-recipe2.html).

```css
* { 
    margin:0; 
    padding:0; 
}
body { 
   font: 100%/1.5 "Lucida Grande", "Lucida Sans Unicode", Verdana, sans-serif; 
   color : #333;
} 
.wrapper  { 
	max-width : 840px; 
	margin : 0 auto;
	margin-top : 50px;
}
.content_main {
	float: left;
	width : 50%;
	padding : 16px 0;
}

.content_sub { 
	float : left;
	width : 50%;
	padding : 16px 0; 
}
```
Note the footer. Because both columns have been floated it can wrap.

```css
footer {
    clear: both;
}
```

Faux columns

```css
.content { 
  background : url(../img/html.png) repeat-y 50% 50%;
}
```
Note that we cannot see the background image. The content div has collapsed because its direct children have been floated. We have looked at a number of methods that can be used to prevent collapsing. E.g.:

```css
.content { 
  background : url(../img/html.png) repeat-y 50% 50%;
  float: left;
}
```

Here we will use the clear fix method. 

```css
.content:after { 
	content:"."; 
	display:block; 
	height:0; 
	clear:both; 
	visibility:hidden; 
}
```

The method uses `:after` to insert a character after the div and then sets it to `display: block` and `clear: both` to prevent collapsing.

Since box collapsing is rather common let's create a generic class that we can use elsewhere.

Change the selector and updated the method to something shorter and more modern:

```css
.cf:before,
.cf:after {
    content: " ";
    display: table;
}

.cf:after {
    clear: both;
}
```

Add the cf class to the content div.

We'll return to the :before and :after pseudo-classes later.

##The Branding

Add the green background to the branding div.

```css
.branding {
	position : relative;
	height : 120px;
	background :#88a308;
	border-radius: 8px 8px 0px 0px;
}
```

Image replacement   USE firebug - to show width/height related to image

```css
.branding h1 { 
	position: absolute;
	top: 0px; 
	left: 0px;
	background: url(../img/h1.png) no-repeat;
}
```

Add absolute / relative positioning and create a viewable area for the image. (Note: we can get the image dimensions via the inspector.) 

`@import url(futura/stylesheet.css);`

```css
.branding h1 { 
	position : absolute; 
	top: -80px; 
	left:-100px;
	z-index: 90;
	padding-left: 260px;
	padding-top: 90px;
	background: url(../img/basil.png) no-repeat;
	font-family: FuturaStdLight, sans-serif; 
	font-weight: normal;
	color:#fff;
	font-size: 76px;
}
```


```css
.branding h1 {
    transform: translateY(-80px) translateX(-100px);
	padding-left: 260px;
	padding-top: 90px;
	background: url(../img/basil.png) no-repeat;
	font-family: FuturaStdLight, sans-serif; 
	font-weight: normal;
	color:#fff;
	font-size: 76px;
}
```

Note:

```html
<div class="branding">
	<h1>Basilica!</h1>
	<a class="beta" href="#">Beta</a>
</div>
```

```css
.branding a.beta {
	background: url("../img/beta.png") no-repeat;
    color:#fff;
    font-size: 1.5rem;
	position: absolute; 
	z-index: 300;
	top:-20px; 
    right:-10px;
	width:85px;
	height:85px;
    line-height:85px;
	text-align:center;
	text-transform: uppercase;
	transform: rotate(12deg);
}
```

```css
.branding a.beta:hover {
	transform: rotate(0deg) scale(1.2);
}
```


```css
.branding a.beta {
	...
	transition: all 1s ease;
}
```

Add the link to our font squirrel css.

```css
@import url(futura/stylesheet.css);
```



##Homework

1. 
















