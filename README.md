# qa-style-sheet

[Moved from Google Project Hosting.](https://code.google.com/p/qa-style-sheet/)

The QA style sheet [https://plus.google.com/+JensOMeiert/posts/KGcMaJCP5wY looks for a new owner]. [http://meiert.com/en/contact/ Contact Jens.]

----

*Important:* Version 1.0 of the QA style sheet used an background image hosted on Google Code to inform about updates. This does not work reliably due to Google Code forcing files to be downloaded. Please update to version 1.1 which fixes this problem and also adds a status indicator (“QA check done”).

----

The QA style sheet highlights specific HTML problems like use of deprecated elements, inaccessible images, layout tables, empty elements, or styling-related maintenance issues. Theoretically, it is “unobtrusive” in a sense that when everything’s fine it won’t cause any visible changes.

## 3 Ways to Use the QA Style Sheet

 # Use it on demand as a *[http://hell.meiert.org/core/html/qa-bookmarklet.html bookmarklet]*: Add the bookmarklet or favelet, respectively, to your bookmarks and access it when needed. When customizing the style sheet better [http://www.peterbe.com/plog/blogitem-040406-1/compressor compress it], [http://www.squarefree.com/userstyles/make-bookmarklet.html generate a new bookmarklet], but make sure to add {{{%20newSS.id%20=%20'x-qa';}}} to the bookmarklet code to avoid false positives when it comes to style sheet references on a page (this assumes you’re keeping the {{{#x-qa}}} selector in the QA style sheet too).
 # Use it permanently as a user style sheet with your browser (userContent.css for Gecko browsers). For more information please see [http://css-discuss.incutio.com/?page=UserStylesheets documentation at CSS-Discuss] or [http://webdesign.about.com/od/css/ht/htcssuserfirefo.htm at About.com]. It’s easy though.
 # Temporarily import the style sheet in your project’s default style sheet. Do not forget to remove the style sheet reference after testing.

## User Agent Support

The style sheet is supported differently across browsers as it makes some use of CSS 3 selectors, and when it comes to warnings for images, at least Internet Explorer might display errors that must not necessarily be there. To get the most of the QA style sheet test respective pages with recent releases of Firefox, Safari, Chrome, or Opera.

## Background and Design Considerations

While Eric Meyer once published a [http://meyerweb.com/eric/thoughts/2007/09/07/diagnostic-styling/ comparable style sheet], this QA style sheet has a slightly different scope. It spots the following problems, indicated in yellow (warning) and red (error) assuming a modern browser:

 * Errors:
   * deprecated elements like {{{applet}}}, {{{basefont}}}, {{{center}}}, {{{dir}}}, {{{font}}}, {{{isindex}}}, {{{menu}}}, {{{s}}}, {{{spacer}}}, {{{strike}}}, and {{{u}}};
   * layout tables (nested tables, to be precise);
   * images ({{{img}}} elements) without any {{{alt}}} attribute;
   * anchors with an empty {{{href}}} attribute thus pointing to nothing;
   * {{{style}}} attributes.
 * Warnings:
   * images with an empty {{{alt}}} attribute;
   * anchors linking GIF, JPG, or PNG images as well as PDF documents;
   * empty {{{p}}}, {{{li}}}, {{{th}}}, {{{td}}}, {{{div}}}, and {{{span}}} elements unless they’re using an {{{id}}} attribute;
   * {{{style}}} elements;
   * more than one {{{link}}} elements.

----

The QA style sheet is currently unmaintained (as of August 19, 2013).