#swIMG.js

swIMG is a simple JavaScript image viewer with no overloading sundry frills.

#### [Documentation](http:thielicious.github.io/#swimg_doc) | [Changelog](http:thielicious.github.io/#swimg_clog) | [Downloads](http:thielicious.github.io/#swimg_dls) | [Examples](http:thielicious.github.io/#swimg_demo) | [License](http:thielicious.github.io/#swimg_lic) ####

---
<br>

##INTRODUCTION

Built with JavaScript 1.8.5(ECMAScript 5 and jQuery v3.11)<br>
For a livedemo click above on **Examples**

**swIMG** ('sw': abbr. for 'switch') is a fullsize image viewer for a specified thumbnail gallery which instantly works right after implementation.

### ***'Straight to the point.'***

This simple gallery is an alternative contrast to the overwhelmingly complicated and slow-loading gallery APIs in the rest of the web. By standard, it extracts the image source of the thumbnails and shows them in fullsize. This script can be easily adjusted in the configuration.
<br>
<br>

## SETUP INFORMATION

swIMG is not a stand-alone API, it uses **jQuery** syntax. This library is required in order to run swIMG.
Click to download:

» [jQuery v3.10+](https://code.jquery.com/jquery-3.1.0.min.js)

Optionally, the additional PlugIn **jgestures** for mobile control can be embedded into the DOM. There is no configuration needed. This PlugIn is not required - once jgestures is detected it will be applied immediately for default mobile control. <br>
Click to download:

» [jgestures v0.90.1](https://jgestures.codeplex.com/releases/view/117280)

Click **swIMG.js** below and then download/link/clone/git the API:

» [swIMG.js](http://thielicious.github.io/#swimg_dls)

<br>
For an overview of all versions and bug fixes please check the [Changelog](http://thielicious.github.io/#swimg_clog).

<br>

**1\.** Once all necessary files have been downloaded, simply embed these in your &lt;head> element of your page.

		

	<head>
	  <script src="scripts/jquery.js"></script>
	  <script src="scripts/jgestures.js"></script> <-- optional
	  <script src="scripts/swIMG.js"></script>
	</head>
		

		

**2\.** Next, execute swIMG() at the top of your HTML code. For example, after or inside the <strong>&lt;/head></strong> tag.

		

	</head>
	  <script> swIMG(); </script>
	<body>
		

		

**3\.** At last, the gallery as a parent container must be specified with the class name swIMG as well as the thumbnails with the name sw_image.

		

	<div class="swIMG">
	  <img src="images/clouds.jpg" class="sw_image"/>
	  <img src="images/trees.jpg" class="sw_image"/>
	  <img src="images/cats.jpg" class="sw_image"/>
	</div>
		

		

When these class elements have not been found, a notification alert will pop up reminding you to fix it. After this implementation it's ready to perform. Simply click on any of the thumbnails. Feel free to check out the Examples below.
<br>
<br>

##EXAMPLES (***CodePen.io***)

####Demos of different adjustments:

» [Images extracted from thumbnails](http://codepen.io/thielicious/pen/wzLRvO)<br>
» [Images extracted from background](http://codepen.io/thielicious/pen/YGopzm)<br>
» [Images from a directory](http://codepen.io/thielicious/pen/dpBQoX)<br>
» [Limited image count](http://codepen.io/thielicious/pen/KgjbRM)<br>
» [Image increment](http://codepen.io/thielicious/pen/rMEoMj)<br>
» [Visual changes](http://codepen.io/thielicious/pen/RGzEmz)<br>
<br>


####If you encounter any bugs, feel free to open up an [issue](https://github.com/thielicious/swIMG.js/issues), thank you.<br>
---
[thielicious.github.io] (http://thielicious.github.io)