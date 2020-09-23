<div align="center">

## Changing the opacity \(transparency\) of images using JavaScript


</div>

### Description

See how CSS and JavaScript can be used to change the opacity of images.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[John John](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/john-john.md)
**Level**          |Intermediate
**User Rating**    |4.5 (50 globes from 11 users)
**Compatibility**  |
**Category**       |[Graphics](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/graphics__2-75.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/john-john-changing-the-opacity-transparency-of-images-using-javascript__2-3206/archive/master.zip)





### Source Code

<p><b><font size="4">Changing the opacity (transparency) of images using
JavaScript</font></b></p>
<p>I think this technique is particularly useful and unique- using JavaScript to
change the opacity of an image! The technique works in both IE4+ and NS6+, and
can be used to create some interesting &quot;fading&quot; effects. Let's get
started!</p>
<p>In IE4+, you can adjust the opacity of an image using the STYLE attribute:</p>
<pre>&lt;img src=&quot;ball.gif&quot; <b>style=&quot;filter:alpha(opacity=50)&quot;</b>&gt;</pre>
<p>I've highlighted the main code. A value of 50 makes this image 50% oblique
(or transparent). You can use a number between 0-100, where 0 would make the
image disappear.</p>
<p>In NS6+, the code needed is a little bit different:</p>
<pre>&lt;img src=&quot;ball.gif&quot; <b>style=&quot;-moz-opacity:0.5&quot;</b>&gt;</pre>
<p>Here the accepted range of values are 0 to 1, where 0 would make the image
disappear.</p>
<p>You're probably now asking- how can I combine the two HTML above to make
opacity specification work in both IE4+ and NS6+? Just define one STYLE
attribute and put the two definitions inside it, separating the two with a semi
colon:</p>
<pre>&lt;img src=&quot;ball.gif&quot; <b>style=&quot;filter:alpha(opacity=50); -moz-opacity:0.5&quot;</b>&gt;</pre>
<p><b><font size="4">Using JavaScript to alter opacity on the fly</font></b></p>
<p>This is where things get interesting and useful- using JavaScript to alter
the value of the image's opacity! By doing so, you can make images fade in or
out, for example.</p>
<p>The JavaScript syntax to change an image's opacity after it's been defined in
the HTML is:</p>
<pre>ImageObj.style.filters.alpha.opacity=90 //IE4 syntax
ImageObj.style.MozOpacity=0.9     //NS6 syntax</pre>
<p>So for example, here's a simple script that adds a &quot;lighting up&quot;
effect to your images as the mouse hovers over and out:</p>
<pre>&lt;script>
function lightup(imageobject, opacity){
if (navigator.appName.indexOf("Netscape")!=-1&amp;&amp;parseInt(navigator.appVersion)>=5)
imageobject.style.MozOpacity=opacity/100
else if (navigator.appName.indexOf("Microsoft")!=-1&amp;&amp;parseInt(navigator.appVersion)>=4)
imageobject.filters.alpha.opacity=opacity
}
&lt;/script>
&lt;img src="test.gif" style="filter:alpha(opacity=50); -moz-opacity:0.5"
onMouseover="lightup(this, 100)" onMouseout="lightup(this, 30)"></pre>
<p>If you want to see a more complicated &quot;lighting up&quot; effect, check
out <a href="http://www.dynamicdrive.com/dynamicindex4/highlightgrad.htm"><b>Gradual
highlight script</b></a> by Dynamic Drive. It uses basically the same technique
as I do, though the opacity is changed incrementally.</p>

