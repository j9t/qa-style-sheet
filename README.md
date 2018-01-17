# QA Style Sheet

The QA style sheet [looks for a new owner](https://plus.google.com/+JensOMeiert/posts/KGcMaJCP5wY). [Contact Jens.](https://meiert.com/en/contact/)

---

The QA style sheet highlights specific HTML problems like use of deprecated elements, inaccessible images, layout tables, empty elements, or styling-related maintenance issues. Theoretically, it is “unobtrusive” in a sense that when everything’s fine it won’t cause any visible changes.

## 3 Ways to Use the QA Style Sheet

* Use it on demand as a [**bookmarklet**](https://hell.meiert.org/core/html/qa-bookmarklet.html): Add the bookmarklet or favelet, respectively, to your bookmarks and access it when needed. When customizing the style sheet better [compress it](https://uitest.com/en/misc/#optimization), [generate a new bookmarklet](http://www.squarefree.com/userstyles/make-bookmarklet.html), but make sure to add `%20newSS.id%20=%20'x-qa';` to the bookmarklet code to avoid false positives when it comes to style sheet references on a page (this assumes you’re keeping the `#x-qa` selector in the QA style sheet too).
* Use it permanently as a user style sheet with your browser (userContent.css for Gecko browsers). For more information please see [documentation at CSS-Discuss](http://css-discuss.incutio.com/?page=UserStylesheets) or [at About.com](http://webdesign.about.com/od/css/ht/htcssuserfirefo.htm). It’s easy though.
* Temporarily import the style sheet in your project’s default style sheet. Do not forget to remove the style sheet reference after testing.

## User Agent Support

The style sheet is supported differently across browsers as it makes some use of CSS&nbsp;3 selectors, and when it comes to warnings for images, at least Internet Explorer might display errors that must not necessarily be there. To get the most of the QA style sheet test respective pages with recent releases of Firefox, Safari, Chrome, or Opera.

## Background and Design Considerations

While Eric Meyer once published a [comparable style sheet](https://meyerweb.com/eric/thoughts/2007/09/07/diagnostic-styling/), this QA style sheet has a slightly different scope. It spots the following problems, indicated in yellow (warning) and red (error) assuming a modern browser:

* Errors:
  * deprecated elements like `applet`, `basefont`, `center`, `dir`, `font`, `isindex`, `menu`, `s`, `spacer`, `strike`, and `u`;
  * layout tables (nested tables, to be precise);
  * images (`img` elements) without any `alt` attribute;
  * anchors with an empty `href` attribute thus pointing to nothing;
  * `style` attributes.
* Warnings:
  * images with an empty `alt` attribute;
  * anchors linking GIF, JPG, or PNG images as well as PDF documents;
  * empty `p`, `li`, `th`, `td`, `div`, and `span` elements unless they’re using an `id` attribute;
  * `style` elements;
  * more than one `link` elements with `rel=stylesheet` attribute.

---

The style sheet is somewhat unmaintained (as of February 4, 2017). [Contributions welcome.](https://github.com/j9t/qa-style-sheet/issues/new)