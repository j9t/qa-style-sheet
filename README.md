# qa-style-sheet

The QA style sheet <a href="https://plus.google.com/+JensOMeiert/posts/KGcMaJCP5wY">looks for a new owner</a>. <a href="http://meiert.com/en/contact/">Contact Jens.</a>

----

The QA style sheet highlights specific HTML problems like use of deprecated elements, inaccessible images, layout tables, empty elements, or styling-related maintenance issues. Theoretically, it is “unobtrusive” in a sense that when everything’s fine it won’t cause any visible changes.

## 3 Ways to Use the QA Style Sheet

* Use it on demand as a <a href="http://hell.meiert.org/core/html/qa-bookmarklet.html"><strong>bookmarklet</strong></a>: Add the bookmarklet or favelet, respectively, to your bookmarks and access it when needed. When customizing the style sheet better <a href="http://uitest.com/en/misc/#optimization">compress it</a>, <a href="http://www.squarefree.com/userstyles/make-bookmarklet.html">generate a new bookmarklet</a>, but make sure to add <code>%20newSS.id%20=%20'x-qa';</code> to the bookmarklet code to avoid false positives when it comes to style sheet references on a page (this assumes you’re keeping the <code>#x-qa</code> selector in the QA style sheet too).
* Use it permanently as a user style sheet with your browser (userContent.css for Gecko browsers). For more information please see <a href="http://css-discuss.incutio.com/?page=UserStylesheets">documentation at CSS-Discuss</a> or <a href="http://webdesign.about.com/od/css/ht/htcssuserfirefo.htm">at About.com</a>. It’s easy though.
* Temporarily import the style sheet in your project’s default style sheet. Do not forget to remove the style sheet reference after testing.

## User Agent Support

The style sheet is supported differently across browsers as it makes some use of CSS 3 selectors, and when it comes to warnings for images, at least Internet Explorer might display errors that must not necessarily be there. To get the most of the QA style sheet test respective pages with recent releases of Firefox, Safari, Chrome, or Opera.

## Background and Design Considerations

While Eric Meyer once published a <a href="http://meyerweb.com/eric/thoughts/2007/09/07/diagnostic-styling/">comparable style sheet</a>, this QA style sheet has a slightly different scope. It spots the following problems, indicated in yellow (warning) and red (error) assuming a modern browser:

* Errors:
  * deprecated elements like <code>applet</code>, <code>basefont</code>, <code>center</code>, <code>dir</code>, <code>font</code>, <code>isindex</code>, <code>menu</code>, <code>s</code>, <code>spacer</code>, <code>strike</code>, and <code>u</code>;
  * layout tables (nested tables, to be precise);
  * images (<code>img</code> elements) without any <code>alt</code> attribute;
  * anchors with an empty <code>href</code> attribute thus pointing to nothing;
  * <code>style</code> attributes.
 * Warnings:
  * images with an empty <code>alt</code> attribute;
  * anchors linking GIF, JPG, or PNG images as well as PDF documents;
  * empty <code>p</code>, <code>li</code>, <code>th</code>, <code>td</code>, <code>div</code>, and <code>span</code> elements unless they’re using an <code>id</code> attribute;
  * <code>style</code> elements;
  * more than one <code>link</code> elements.

----

The QA style sheet is currently unmaintained (as of August 19, 2013).