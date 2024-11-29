# QA Style Sheet

The QA style sheet [looks for a new owner](https://plus.google.com/+JensOMeiert/posts/KGcMaJCP5wY). [Please contact Jens.](https://meiert.com/en/contact/)

---

The QA style sheet highlights specific HTML problems like use of deprecated elements, inaccessible images, layout tables, empty elements, or styling-related maintenance issues. Theoretically, it is “unobtrusive” in a sense that when everything’s fine it won’t cause any visible changes.

## 3 Ways to Use the QA Style Sheet

1. Use it on demand as a [**bookmarklet**](https://j9t.github.io/qa-style-sheet/bookmarklet.html): Add the bookmarklet or favelet, respectively, to your bookmarks and access it when needed. When customizing the style sheet better [compress it](https://frontenddogma.com/tools/#exploration-code-optimization), [generate a new bookmarklet](https://www.squarefree.com/userstyles/make-bookmarklet.html), but make sure to add `%20newSS.id%20=%20'x-qa';` to the bookmarklet code to avoid false positives when it comes to style sheet references on a page (this assumes you’re keeping the `#x-qa` selector in the QA style sheet, too).

2. Temporarily import the style sheet in your project’s default style sheet. Do not forget to remove the style sheet reference after [testing](https://j9t.github.io/qa-style-sheet/test.html).

3. Use it permanently as a user style sheet with your browser (userContent.css for Gecko browsers). For more information please see [documentation at CSS-Discuss](https://web.archive.org/web/20180105053457/http://css-discuss.incutio.com/?page=UserStylesheets) or [at About.com](https://web.archive.org/web/20161120013248/http://webdesign.about.com/od/css/ht/htcssuserfirefo.htm). It’s easy though.

## User Agent Support

The style sheet is supported differently across browsers as it makes some use of CSS 3 selectors, and when it comes to warnings for images, at least Internet Explorer might display errors that must not necessarily be there. To get the most of the QA style sheet test the respective pages with recent releases of Firefox, Safari, Chrome, or Opera.

## Background and Design Considerations

While Eric Meyer once published a [comparable style sheet](https://meyerweb.com/eric/thoughts/2007/09/07/diagnostic-styling/), this QA style sheet has a slightly different scope. It spots the following problems, indicated in yellow (warning) and red (error) assuming a modern browser:

* Errors:
  * deprecated elements like `applet`, `basefont`, `center`, `dir`, `font`, `isindex`, `menu`, `spacer`, or `strike`;
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

The style sheet is unmaintained (as of November 29, 2024). [Contributions welcome.](https://github.com/j9t/qa-style-sheet/issues/new)