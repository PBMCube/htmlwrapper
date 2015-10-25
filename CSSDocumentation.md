# CSS #
Wrapper uses CSS style sheets much like normal HTML but because Wrapper uses the Flash Player to render you can also use anything that Flash/Flex/ActionScript can. Wrappers CSS support is extend far beyond what many people think is possible with these technologies but also simplifies some core features. This article will explain the core of what you can do with CSS within Wrapper.

## Base Wrapper styles: ##
To make sure this Wrapper covers the your HTML page your style sheet should start with this to assure the content is 100% and to the edge. This is the last CSS hack you will have to do on your whole site because after this everything is rendered with Wrapper.
```
/* hide from ie on mac \*/
html {
	height: 100%; 
	overflow: auto;
}
#content {
	height: 100%;
	font-family: arial;
}
/* end hide */
body {
	height: 100%;
	margin: 0; padding: 0;
}
```

Before you get to far into this, the most fundamental thing to understand about how Wrapper renders everything is it's separation between text and elements. If you start a P tag (<p>) or any text node you have started a text block and can not add a structural element into this text block. The text is then under the limitations of what you can render inside of the text field in the flash player. This also means that your structural elements are not under the control of text flow. If you can make this jump and understand what this means to the structure of your page there is nothing you can't make, you just have to understand how to make it.<br>
<br>
How to write CSS in Wrapper:<br>
In Wrapper the structure of CSS is simple.<br>
<br>
<b>Node Styles:</b>
<pre><code>div { background-color: #FF9900; } <br>
&lt;div /&gt;<br>
</code></pre>
would make all div nodes orange.<br>
<br>
<b>ID Styles:</b>
<pre><code>#idStyle { background-color: #0000FF; } <br>
&lt;div id="idStyle" /&gt;<br>
</code></pre>
would make any node with the id of idStyle blue.<br>
<br>
<b>Class Styles:</b>
<pre><code>.classStyle { background-color: #FF0000; }<br>
&lt;div class="classStyle" /&gt;<br>
</code></pre>
would make any node with the class of classStyle red.<br>
<br>
<b>All together:</b>
<pre><code>&lt;div id="idStyle" class="otherStyle classStyle" /&gt;<br>
</code></pre>
These styles can also combined by making nodes like this.<br>
<br>
What color would the element become? This would be read like this, overriding similar styles in order:<br>
First node styles, then class styles from left to right ( you can have more then one separated by spaces ), then id styles.<br>
Also keep in mind you should always have unique id's, dont have two nodes called "box1".<br>
You also can't use CSS drilling or commas to denote multiple accessors but this isn't needed if everything else is done like above.<br>
Wrapper also has style bubbling so if you do not define a property that is needed Wrapper will look to the nodes parent for the style.<br>
<br>
<b>Wrapper CSS Properties:</b>
Inside of your styles you can use camelCase or the normal css names with dashes ( marginLeft, margin-left )) for all multi word properties.<br>
<br>
<br>
<br>
<br>
<h2>CSS Coordinates, Positioning:</h2>
<b>position:</b>
Position can be set to auto, relative, or absolute defining an elements coordinate systems.<br>
<br>
<code>position: auto;</code> is Wrapper's default, much like HTML will enable elements to flow relative to there size.<br>
<br>
<code>position: relative;</code> will switch to top, left/ x, y coordinate systems relative to the parent element. This is the flash player default.<br>
<br>
<code>position: absolute;</code> will switch to top, left/ x, y coordinate systems relative to the page. This is work in progress.<br>
<br>
<br>
<b>left:</b>
Left is the same as "x" in a cartesian coordinate system defining the space from the left coordinates systems 0 point. It's default is 0. Left is also what you would use to center or position something relative to something else horizontally. There is no floats or text-align within Wrappers element positioning that will do the same currently (on a side note you can use text-align inside of a text element).<br>
<code>left: 10px;</code> In Wrapper you dont need to define px's but in standard CSS you do, so it's good practice.<br>
<code>left: 10%;</code> Percentages define the distance relative to the width of your parent.<br>
<br>
<code>left: center;</code> Defines the center point relative to the width of your parent.<br>
<br>
<code>left: right;</code> Right aligns an element to the parent containers width.<br>
<br>
<br>
<b>top:</b>
Top is the same as "y" in a cartesian coordinate system defining the space from the top of the coordinates systems 0 point. It's default is 0. Top is also what you would use to center or position something relative to something else vertically. This works much better then in standard HTML/CSS<br>
<br>
<code>top: 10px;</code> In Wrapper you dont need to define px's but in standard CSS you do, so it's good practice.<br>
<br>
<code>top: 10%;</code> Percentages define the distance relative to the height of your parent.<br>
<br>
<code>top: center;</code> Defines the center point relative to the height of your parent.<br>
<br>
<code>top: bottom;</code> Bottom aligns an element to the parent containers height.<br>
<br>
<br>
<b>width:</b>
Define the width of any block. The default is 100%<br>
<br>
<code>width: 10px;</code>

<code>width: 10%;</code>


<b>height:</b>
Define the height of any block. The default is 100%<br>
<br>
<code>height: 10px;</code>

<code>height: 10%;</code>


<b>margins:</b>
Margin is the space around or on the outside of an element. You can define each side individually, all at once or shorthand all in one line. Negative number will work but you will run into problems in some cases, try not to use negative numbers if you dont need to.<br>
<br>
<code>margin: 8px 2px 8px 2px;</code> This is short hand for defining values in this order: top, right, bottom, left.<br>
<br>
<code>margin: 8px;</code> Is defining all margin values to be the same, 8 pixels all around in this case.<br>
<br>
<code>margin-top: 8px;</code> Each value can also be defined independently like so.<br>
<br>
<code>margin-right: 8px;</code>

<code>margin-bottom: 8px;</code>

<code>margin-left: 8px; </code>


<b>padding:</b>
Padding is the space inside an element or amount of space padding the content of the element. You can define each side individually, all at once or shorthand all in one line. Negative number will work but you will run into problems in some cases, try not to use negative numbers if you dont need to.<br>
<br>
<code>padding: 8px 2px 8px 2px;</code> This is short hand for defining values in this order: top, right, bottom, left.<br>
<br>
<code>padding: 8px;</code> Is defining all padding values to be the same, 8 pixels all around in this case.<br>
<br>
<code>padding-top: 8px; </code> Each value can also be defined independently like so.<br>
<br>
<code>padding-right: 8px;</code>

<code>padding-bottom: 8px;</code>

<code>padding-left: 8px;</code>



<h2>Display Options:</h2>

<b>rotation:</b>
Rotation isn't something you can normally use in standard CSS but you can in Wrapper. The thing you need to be careful about is when a child elements edge extends outside of that elements parent. Rotation is defined in degrees.<br>
<code>rotation: 180;</code> This would be upside-down.<br>
<br>
<b>opacity:</b>
The alpha or opacity can be set on a clip with this property. The value is set with a percentage represented from 0 to 1. So 0.5 would be 50%. The default is 1.<br>
<br>
<b>hidden:</b>
To change the visibility of an element set this to true or false.<br>
<br>
<b>cache-as-bitmap:</b>
To take advantage of the speed of bitMap rendering you can try setting this to true. It will greatly speed things up that are small on your page but not recommended for larger container clips. Default is false.<br>
<br>
<b>button-mode:</b>
To get the hand to show up when you rollover something you can set button-mode to true. The default is false.<br>
<br>
<b>blend-mode:</b>
Like in Photoshop or Flash you can set blend modes, many really cool things can be made with this but it will slow things down considerably if to much of it is used. Here are the blend-mode options; add, alpha, darken, difference, erase, hardlight, invert, layer, lighten, multiply, normal, overlay, screen, subtract.<br>
<br>
<b>filters:</b>
Bitmap Filters can be added to any element with JSON. These are the current options; bevel, blur, colorMatrix, dropShadow, and glow. Here are some examples of using them.<br>
<pre><code>filters: json('[{"type":"blur","blurX":8,"blurY":8,"quality":1}]');<br>
<br>
filters: json('[{"type":"glow","color":0,"alpha":0.9,"blurX":8,"blurY":8,"strength":1,"quality":1,"inner":true }]');<br>
<br>
filters: json('[{"type":"bevel","color":0,"alpha":0.9,"blurX":8,"blurY":8,"strength":1,"quality":1,"inner":true }]');<br>
<br>
filters: json('["type":"bevel","distance":3,"angle":0,"highlightColor":16000000,"highlightAlpha":1,"shadowColor":0,"shadowAlpha":1,"blurX":3,"blurY":3,"strength":1,"quality":1,"fillType":"inner"}]');<br>
<br>
filters: json('["type":"dropshadow","distance":3,"angle":0,"color":0,"alpha":1,"blurX":3,"blurY":3,"strength":1,"quality":1,"inner":true,"knockout":true}]');<br>
<br>
filters: json('[{"type":"colormatrix", "matrix":[1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0]}]');<br>
</code></pre>


<h2>Background Fills:</h2>
Backgrounds or fills can be defined in normal CSS style or with javaScript object notation (JSON). The reason that you might want to write your fill in the more complex syntax is if you wanted to define a more complex fill like a radial gradient but all the other forms of fills can be defined like this as well. For more documentation on gradient fills see here and for basic fills see here.<br>
<pre><code>background: #FF3300; <br>
background-color: #FF3300; <br>
background-image: url("assets/images/cool.jpg"); <br>
fill: json('{ "type":"none" }');<br>
fill: json('{ "type":"solid", "color":12345678, "alpha":1 }');<br>
fill: json('{ "type":"gradient", "kind":"linear", "colors":[0,16000000], "alphas":[1,1], "ratios":[0,255], "w":100, "h":100, "r":30, "tx":0, "ty":0, "spread":"pad","interpolation":"RGB","focalpoint":1 }'); <br>
fill: json( { "type": "image", "url":"images/img.jpg" }');<br>
</code></pre>



<h2>Border Line Styles:</h2>
Border-color will define a one point line around your element in the specified color, if you would like something more complex you can define a line object in JSON syntax. For more documentation on complex line styles see here.<br>
<pre><code>border-color: #FF3300;<br>
border: json( { "type":"none" } );<br>
border: json( { "type":"solid", "weight":5, "color":16000000, "alpha":1 } );<br>
border: json( { "type":"gradient", "weight":5, "kind":"linear", "colors":[0,16000000], "alphas":[1,1], "ratios":[0,255], "w":100, "h":100, "r":30, "tx":0, "ty":0, "spread":"pad","interpolation":"RGB","focalpoint":1 } );<br>
</code></pre>



<h2>Shapes:</h2>
In standard CSS everything is a rectangle, this isn't true in Wrapper, you can have any number of shapes. If you define nothing of course you start with a rectangle but you can also define something as something else. The shapes that are based off of circles have there registration points in the center, because of this you might need to move an object to a different place to get it to work. You might also have positioning problems if your shape extends the outside of it's parent. Move the children in side of there parent and everything should be fine.<br>
<br>
Both none and box are just rectangles<br>
<code>shape: json( { "type":"none" } );</code>

<code>shape: json( { "type":"box" } );</code>


<b>circle or oval</b>

<code>shape: json( { "type":"ellipse", "w":20, "h":20 } );</code>


<b>rounded box, h(height) is optional it will take the value from w. This is width and height of the corner.</b>

<code>shape: json( { "type":"rounded", "w":20, "h":20 } ); </code>


<b>rounded box with all corners different</b>

<code>shape: json( { "type":"roundedComplex", "tl":20, "tr":20, "br":20, "bl":20 } ); </code>


<b>polygon, octagon, triangle, whatever, you define the points</b>

<code>shape: json( { "type":"polygon", "angle":20, "points":20 } );				</code>


<b>wedge or pie chart</b>

<code>shape: json( { "type":"wedge", "startAngle":120, "arc":310, "radius":100, "yRadius":100 } );</code>


<b>burst</b>

`shape: json( { "type":"burst", "angle":20, "points":20, "innerRadius":20,<br>
"outerRadius":20 } );`<br>
<br>
<br>
<b>star</b>

<code>shape: json( { "type":"star", "angle":20, "points":20, "innerRadius":20, "outerRadius":20 } );</code>





<h2>Text Styles:</h2>

<b>color:</b>
Only hexadecimal color values are supported. Named colors (such as blue) are not supported. Colors are written in the following format: #FF0000.<br>
<code>color: #FF9900;</code>

<b>display:</b>
Supported values are inline, block, and none.<br>
<code>display: block;</code>

<b>font-file:</b>
Wrapper supports custom font loading, you can define a font to load once and have access to it in any style by defining your font-family.<br>
<code>font-file: url("assets/fonts/MyCoolFont.swf");</code>

<b>font-family:</b>
A comma-separated list of fonts to use, in descending order of desirability. Any font family name can be used.<br>
<br>
<b>font-size:</b>
Define the point size of the font.<br>
<br>
<b>font-style:</b>
Recognized values are normal and italic.<br>
<br>
<b>font-weight:</b>
Recognized values are normal and bold.<br>
<br>
<b>kerning:</b>
Recognized values are true and false. Kerning is supported for embedded fonts only. Certain fonts, such as Courier New, do not support kerning. The kerning property is only supported in SWF files created in Windows, not in SWF files created on the Macintosh. However, these SWF files can be played in non-Windows versions of Flash Player and the kerning still applies.<br>
<br>
<b>letter-spacing:</b>
The amount of space that is uniformly distributed between characters. The value specifies the number of pixels that are added after each character. A negative value condenses the space between characters.<br>
<br>
<b>line-height / leading:</b>
The amount of space that is uniformly distributed between lines. The value specifies the number of pixels that are added after each line. A negative value condenses the space between lines.<br>
<br>
<b>padding-left:</b>
Just like the padding of elements.<br>
<br>
<b>padding-right:</b>
Just like the padding of elements.<br>
<br>
<b>text-align:</b>
Recognized values are left, center, right, and justify.<br>
<br>
<b>text-decoration:</b>
Recognized values are none and underline.<br>
<br>
<b>text-indent:</b>
How far the text is indented from the beginning of the line.<br>
<br>
<b>multiline:</b>
Text boxes that should remain a single line should set multiline to false, the default is true.<br>
<br>
<b>word-wrap:</b>
Text boxes that should do not break at the end of the line should set word-wrap to false, the default is true.<br>
<br>
<b>anti-alias-type:</b>
To simplify the anti-alias rendering you can set anti-alias-type to normal, default is advanced. Normal is sometimes better for things that animate.<br>
<br>
<b>selectable:</b>
To prevent the ability to select the text you can set selectable to false, default is true.<br>
<br>
<b>display-as-password:</b>
Password fields normally hide the characters in the fields by obscuring them, use this flag to make this happen.<br>
<br>
<b>condense-white:</b>



<h2>Events:</h2>
In Wrapper's CSS you can also add events. This is a little different then normal and could be missed used but actually works great for things like rollover events, why write something like that over and over. In Wrapper you can put that kind of thing in a style. Events can be added in html or css and are defined inline with json or in an external JSON file. Read the JSON documentation for more information.<br>
<br>
<br>
<h2>More Information:</h2>
For more information about the basics the W3C is a great place to start or reference for what all of this is based on. And a knowledge of how the flash player renders Display Objects and deals with depth is also a big help.<br>
