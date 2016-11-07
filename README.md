<h1>swIMG.js</h1>
swIMG is a simple JavaScript image viewer with no overloading sundry frills.<br>
<br>
<h3>Documentation</h3>
<br>
	<ul>
		<li><a href="#intro">Introduction</a></li>
		<li><a href="#setup">Setup Information</a></li>
		<li><a href="#config">Configuration</a></li>
		<li><a href="#usage">Usage</a></li>
		<li><a href="#future">Future Plans</a></li>
		<li><a href="#demos">Examples</a></li>
	</ul>
	<br><br><br>
INTRODUCTION


Built with JavaScript 1.8.5(ECMAScript 5 and jQuery v3.11)
For a livedemo: see EXAMPLES
Free Licence: click LICENCE for more information.

swIMG ('sw': abbr. for 'switch') is a fullsize image viewer for a specified thumbnail gallery which instantly works right after implementation.

'Straight to the point.'

This simple gallery is an alternative contrast to the overwhelmingly complicated and slow-loading gallery APIs in the rest of the web. By standard, it extracts the image source of the thumbnails and shows them in fullsize. This script can be easily adjusted in the configuration.


SETUP INFORMATION


swIMG is not a stand-alone API, it uses JQuery syntax. This library is required in order to run swIMG. Click to download:

- JQuery v3.10+

Optionally, the additional PlugIn jgestures for mobile control can be embedded into the DOM. There is no configuration needed. This PlugIn is not required - once jgestures is detected it will be applied immediately for default mobile control. Click to download:

- jgestures v0.90.1

Choose swIMG.js at the download section:

- swIMG.js

For an overview of all versions and bug fixes please check the CHANGELOG.


1. Once all necessary files have been downloaded, simply embed these in your <head> element of your page.

		

	<head>
	  <script src="scripts/jquery.js"></script>
	  <script src="scripts/jgestures.js"></script> <-- optional
	  <script src="scripts/swIMGv092.js"></script>
	</head>
		

		

2. Next, execute swIMG() at the bottom of your HTML code. For example, after the closing tag </html> or </body>. It is necessary due to triggered elements which first have to be DOM-ready.

		

	  </body>
	  <script> swIMG(); </script>
	</html>
		

		

3. At last, the gallery as a parent container must be specified with the class name swIMG as well as the thumbnails with the name sw_image.

		

	<div class="swIMG">
	  <img src="images/clouds.jpg" class="sw_image"/>
	  <img src="images/trees.jpg" class="sw_image"/>
	  <img src="images/cats.jpg" class="sw_image"/>
	</div>
		

		

When these class elements have not been found, a notification alert will pop up reminding you to fix it. After this implementation it's ready to perform. Simply click on any of the thumbnails. Feel free to check out the Examples for a live demonstration.


CONFIGURATION


First off, it is important to know that swIMG performs 2 methods of how the fullsize images will be displayed: 'small' and 'large'. With these you determine whether you want the small thumbnails to be loaded inside the gallery or larger images from a given filepath. Certain parameters depend on which method you choose. By default, all parameters are set for small thumbnails.
All other parameters can be configured through Direct Configuration within the function.


[method]
default: 'small'
As explained above, display methods for images in the gallery.
» choose 'small' if you want to display the image source from the thumbnails
» choose 'large' if you would like to display large images from a given path

[imagePath]
default: no path defined
When method is set to 'large', it is required to specify the path to your image folder for the large images.

[parent]
default: '.swIMG'
Defines the parent class element (container/wrapper) which includes all thumbnails.

[thumbs]
default: '.sw_image'
Class element for the thumbnails

[count]
default: 'auto'
Determines how many thumbnails will be applied to run with swIMG.
» choose 'auto' if you want all thumbnails to be applied within the parent container
» set an integer to apply only a specified amount (eg: count : 8,)

[mobile]
default: '640px'
Sets the width for mobile devices. When triggered, following responsive adjustments will occur:
» arrows and close buttons will be deactivated
» images in the gallery view will be fit to screen
» (mobile swipe control will be activated if jgestures.js is embedded, see Setup Information)

[maxSize]
default: '100%'
Maximum size of images in fullsize for mobile devices. By default it's 100%.

[minSize]
default: '80%'
Fullsize images will be resized at 80% (default) of the original size for desktop devices

[bgcolor]
default: '0,0,0'
Background color of the image viewer. To change the color use this syntax: R,G,B.
eg. bgcolor: '255,0,0' for red.

[opacity]
default: '0.8'
Sets the opacity for the background of the viewer, by default it's 0.8. Range is from 0-1 transparent to full.

[arrowColor]
default: 'grey'
Color for the arrow buttons.

[arrowColorHover]
default: 'white'
Color for the mouseover effect on the arrows.

[closeColor]
default: 'grey'
Color for the close button (x).

[closeColorHover]
default: 'white'
Color for the mouseover effect on the close button (x).

[increment]
default: 'false'
Only if the method is set to 'large', huge amount of large images in a folder with increasing numbers can be applied and viewed in fullsize (1.jpg, 2.jpg, 3.jpg etc). Very useful, if the thumbnail count is limited for some reason. For a demo to this please see Examples.
» choose true in order to activate this parameter to display numbered images
» choose false if you want to show individual names in 'LargeImages' see below

[LargeImages]
default: no images are defined
Method must be set to 'large' and increment to 'false' for this parameter. This is an array containing image files with individual names. Make sure that you have imagePath parameter defined for the image folder.
It could look something like this:

		

	LargeImages: [	
	  "clouds.jpg",
	  "trees.jpg",
	  "cats.jpg"
	];
		

		

The index starts from 1, which means that the first thumbnail will show 'clouds.jpg', next one 'trees.jpg' and so on. An example to this can be viewed here.


Direct Configuration

Parameters can be configured within the parentheses of the function swIMG(). For a demonstration, two examples can be seen below.

If you would like to adjust the colors of some elements, do it like the following:

		

	swIMG({
	  bgColor: "0,100,100",
	  opacity: "0.9",
	  arrowColor: "white",
	  closeColorHover: "red"
	});
		

		

And if you wish to change configuration for large images:

		

	swIMG({
	  method: "large",
	  imagePath: "img/large/",
	  LargeImages: [
	    "clouds.jpg",
	    "trees.jpg",
	    "cats.jpg"
	  ]
	});
		

		


For small thumbnails there is no configuration needed, as it's already in the default settings.


USAGE


Currently, the increment only works for images with the extension JPG. As of now, swIMG is able to extract the image path from <img> tags and from Background Images.


SRC-Extraction

		

	<div class="swIMG">
	  <img src="images/clouds.jpg" class="sw_image"/>
	  <img src="images/trees.jpg" class="sw_image"/>
	  <img src="images/cats.jpg" class="sw_image"/>
	</div>
		

		

In the Setup Information you see an example of thumbnails with image sources attached inside a <img> element. The code above is by far the most used pattern. swIMG extracts the image path out of the SRC attribute.


Background-Extraction:

		

	.sw_image {
	  &:nth-child {
	    &(1) { background: url('images/clouds.jpg') } 
	    &(2) { background: url('images/trees.jpg') }
	    &(3) { background: url('images/cats.jpg') }
	  }
	}
		

		

		

	<div class="swIMG">
	  <div class="sw_image"></div>
	  <div class="sw_image"></div>
	  <div class="sw_image"></div>
	</div>
		

		

In some cases, thumbnail images are often placed in the background of an element. For example using CSS. However, swIMG can extract these as well.



Once the class swIMG is implemented, it will check which element the class sw_image is added to. This could be any block element with a modified background-style using CSS, just as <div>, <li> or <nav> etc.


Control:

By a simple click swIMG will perform and the image viewer opens. There are three kinds of switch control to the next and previous image:

» Visual Interface:
   Arrows and close button to switch to next and previous images and close the gallery
» Keyboard Control:
   Arrow keys left and right for switching
» Mobile Control:
   Swipe control to the left and right. (jgestures.js is required, see Setup Information)


Browser Compatibility:

The following browsers have been tested with the API and passed:

    » Mozilla Firefox
    » Microsoft Edge
    » Google Chrome
    » Safari
    » Opera
    » Android Browser

    This API works in all current versions of the mainstream browsers from today and does not require any specific adjustments/plugins and the like.

    Obviously, your browser should have JavaScript to be enabled. Also for mobile browsers as long as it is capable with the jQuery library - jQuery Mobile is not required.

    For issues that might appear in future please let me know by adding your problem at the issues page at GitHub, thank you.


FUTURE PLANS


Following ideas could be possibly taken into consideration:

    » pre-loaded images for quick view
    » adding a description to each of the images
    » more file extensions JPEG/PNG/BMP/GIF...



Although, these ideas are doable, I would rather keep this simple gallery very clean and plain as it is right now. The point here is to have a gallery which has no sundry frills and 'features' in it.


EXAMPLES (CodePen.io)


Demos of different adjustments:

» Images extracted thumbnails
» Images extracted from background
» Images from a directory
» Limited image count
» Image increment
» Visual changes
