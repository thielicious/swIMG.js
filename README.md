#swIMG.js
swIMG is a simple JavaScript image viewer with no overloading sundry frills.

» **[Documentation]**()
» **[Changelog]**()
» **[Downloads]**()
» **[Examples]**()
» **[Licence]**()

---

Built with JavaScript 1.8.5(ECMAScript 5 and jQuery v3.11)
For a livedemo: click above on **Examples**

**swIMG** ('sw': abbr. for 'switch') is a fullsize image viewer for a specified thumbnail gallery which instantly works right after implementation.

## ***'Straight to the point.'***

This simple gallery is an alternative contrast to the overwhelmingly complicated and slow-loading gallery APIs in the rest of the web. By standard, it extracts the image source of the thumbnails and shows them in fullsize. This script can be easily adjusted in the configuration.


## SETUP INFORMATION


swIMG is not a stand-alone API, it uses **JQuery** syntax. This library is required in order to run swIMG.
Click to download:

» [jQuery v3.10+]()

Optionally, the additional PlugIn jgestures for mobile control can be embedded into the DOM. There is no configuration needed. This PlugIn is not required - once jgestures is detected it will be applied immediately for default mobile control. Click to download:

» [jgestures v0.90.1]()

Choose swIMG.js at the download section:

» [swIMG.js]()

For an overview of all versions and bug fixes please check the CHANGELOG.


**1\.** Once all necessary files have been downloaded, simply embed these in your <head> element of your page.

		

	<head>
	  <script src="scripts/jquery.js"></script>
	  <script src="scripts/jgestures.js"></script> <-- optional
	  <script src="scripts/swIMGv092.js"></script>
	</head>
		

		

**2\.** Next, execute swIMG() at the bottom of your HTML code. For example, after the closing tag </html> or </body>. It is necessary due to triggered elements which first have to be DOM-ready.

		

	  </body>
	  <script> swIMG(); </script>
	</html>
		

		

** 3\.** At last, the gallery as a parent container must be specified with the class name swIMG as well as the thumbnails with the name sw_image.

		

	<div class="swIMG">
	  <img src="images/clouds.jpg" class="sw_image"/>
	  <img src="images/trees.jpg" class="sw_image"/>
	  <img src="images/cats.jpg" class="sw_image"/>
	</div>
		

		

When these class elements have not been found, a notification alert will pop up reminding you to fix it. After this implementation it's ready to perform. Simply click on any of the thumbnails. Feel free to check out the Examples below.


## EXAMPLES (*** CodePen.io ***)

### Demos of different adjustments:

» [Images extracted thumbnails]()
» [Images extracted from background]()
» [Images from a directory]()
» [Limited image count]()
» [Image increment]()
» [Visual changes]()
