LESS Zen Grid
=============

Implementation of Zen Grid in LESS, this so called CSS isolation, claims to fix the "sub-pixel rounding" problem.

On stackoverflow i read a question [Is there a LESS framework that uses css-isolation?](http://stackoverflow.com/questions/20901150/css-isolation-framework-for-less). Good question, althought not for SO, it was closed. But wat is CSS isolation? The question refers to: [http://palantir.net/blog/responsive-design-s-dirty-little-secret](http://palantir.net/blog/responsive-design-s-dirty-little-secret). That make some sense, but i still don't full understand.
Okay, [Zen Grids](http://zengrids.com/) use it, [Susy](http://susy.oddbird.net/) has it too and the explained it like:

>Every float is positioned relative to its container, rather than the float before it. It’s a bit of a hack, and removes >content from the flow, so I don’t recommned building your entire layout on isolated floats, but it can be very useful as >a spot-check when rounding errors are really causing you a headache.

Note: Also [The Semantic GRID SYSTEM](http://semantic.gs/) claims a solution for the [sub-pixel rounding issue ](http://tylertate.com/blog/2012/01/05/subpixel-rounding.html). Runs on LESS, SCSS, or Stylus.

Also read [Responsive Grid Frustrations – Susy, Zen and sub-pixel rounding] (http://benfrain.com/responsive-grid-frustrations-susy-zen-and-sub-pixel-rounding/), it's all about that "sub-pixel rounding".

Well okay, all this seems easy to do in <a href="http://www.lesscss.org/">LESS</a> too. Why is it not done before?
Maybe it is not so useful at all.... but try it yourself.

[Zen Grids](http://zengrids.com/) shows an example:

	<div class="container">
	  <article class="content">
		Tha main content. We like semantic HTML ordering.
	  </article>
	  <aside class="aside1">
		An aside.
	  </aside>
	  <aside class="aside2">
		Another aside.
	  </aside>
	  <footer class="footer1">
		A footer.
	  </footer>
	  <footer class="footer2">
		Another footer.
	  </footer>
	</div>
	
The above should be styled or add to the grid by:

	.container {
	 .zen-grid-container; // Apply this mixin to the container.
	}

	.aside1 {
	 .zen-grid-item(2, 1); // Apply this mixin for each grid item in the container.
	}

	.content {
	 .zen-grid-item(4, 3); // Make this grid item span 4 columns. // Position this grid item in the 3rd column.
	}

	.aside2 {
	 .zen-grid-item(1, 7);
	}

	.footer1 {
	 .zen-new-row(); // Apply this mixin to start a new row.
	 .zen-grid-item(3, 5);
	}
	.footer2 {
	 .zen-grid-item(4, 1);
	}
	
To rewrite the above with LESS i made some assumptions:

* gutter method: padding
* support  IE6/7: No
* box-sizing: border-box
* zen-direction: left
* zen-grid-container don't applies `context`, so no sub grids allowed for now?

Drop IE6/7 seems a little weird cause this browsers are the problem in some way. Or not?
If you need the IE6/7, please let me know. It is easy to build in.

Download and Demo
-----------------
Download the files in watch them in your browser. Download includes less.js for client side compiling of the LESS files.


Support
-------
We are always happy to help you. If you have any question regarding this code. [Send us a message](http://www.jamedowebsites.nl/contact/) or contact us on twitter [@JamedoWebsites](http://twitter.com/JamedoWebsites).

Changelog
---------

1.0

* First version

