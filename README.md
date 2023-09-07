# QA Style Sheet

The QA style sheet [looks for a new owner](https://plus.google.com/+JensOMeiert/posts/KGcMaJCP5wY). [Contact Jens.](https://meiert.com/en/contact/)

---

The QA style sheet highlights specific HTML problems like use of deprecated elements, inaccessible images, layout tables, empty elements, or styling-related maintenance issues. Theoretically, it is “unobtrusive” in a sense that when everything’s fine it won’t cause any visible changes.

## 3 Ways to Use the QA Style Sheet

1. Use it on demand as a [**QA style sheet bookmarklet**](javascript:styles='acronym,applet,basefont,bgsound,big,blink,center,dir,font,hgroup,isindex,listing,marquee,menu,nextid,noembed,plaintext,s,spacer,strike,tt,u,xmp{outline:2px%20solid%20#900%20!important}table%20table{outline:2px%20solid%20#900%20!important}img{outline:2px%20solid%20#900%20!important}img[alt]{outline:0%20!important}img[alt=\'\']{outline:2px%20solid%20#fe8%20!important}a[href=\'\']{outline:2px%20solid%20#900%20!important}a[href$=\'.gif\'],a[href$=\'.jpg\'],a[href$=\'.jpeg\'],a[href$=\'.pdf\'],a[href$=\'.png\']{outline:2px%20solid%20#fe8%20!important}p:empty,li:empty,th:empty,td:empty,div:empty,span:empty{outline:2px%20solid%20#fe8%20!important}p[id],li[id],th[id],td[id],div[id],span[id]{outline:0%20!important}[style]{outline:2px%20solid%20#900%20!important}head{display:block%20!important;font:400%2075%/1.5%20verdana,sans-serif%20!important}link{display:inline%20!important}link[rel=\'stylesheet\']%20~%20link[rel=\'stylesheet\']::after,style::before{background:#fe8%20!important;padding:.2em%20!important}link[rel=\'stylesheet\']%20~%20link[rel=\'stylesheet\']::after{content:\'Two%20or%20more%20style%20sheets%20detected%20\\2639\'%20!important}style{display:block%20!important;font-family:courier,monospace%20!important;height:3em%20!important;overflow:hidden%20!important;width:200px%20!important}style::before{content:\'Style%20element%20detected%20\\2639\'%20!important;font:400%201em/1.5%20verdana,sans-serif%20!important}body::before{background:#fff8e7;color:#000;content:\'QA%20check%20done%20\\2713\';display:inline;font-weight:900}body{background-image:url(https://hell.meiert.org/core/png/qa-1.5.png)%20!important}';%20newSS%20=%20document.createElement('link');%20newSS.rel%20=%20'stylesheet';%20newSS.id%20=%20'x-qa';%20newSS.href%20=%20'data:text/css,'%20+%20escape(styles);%20document.documentElement.childNodes[0].appendChild(newSS);%20void%200): Drag the bookmarklet link to your browser’s bookmarks bar or add it to your favorites manually. You can then run the bookmarklet on any page you like by just accessing it in your bookmarks bar or in your favorites. (When customizing the style sheet better [compress it](https://frontenddogma.com/tools/#exploration-code-optimization), [generate a new bookmarklet](https://www.squarefree.com/userstyles/make-bookmarklet.html), but make sure to add `%20newSS.id%20=%20'x-qa';` to the bookmarklet code to avoid false positives when it comes to style sheet references on a page—this assumes you’re keeping the `#x-qa` selector in the QA style sheet, too.)

2. Temporarily import the style sheet in your project’s default style sheet. Do not forget to remove the style sheet reference after testing.

3. Use it permanently as a user style sheet with your browser (userContent.css for Gecko browsers). For more information please see [documentation at CSS-Discuss](https://web.archive.org/web/20180105053457/http://css-discuss.incutio.com/?page=UserStylesheets) or [at About.com](https://web.archive.org/web/20161120013248/http://webdesign.about.com/od/css/ht/htcssuserfirefo.htm). It’s easy though.

## User Agent Support

The style sheet is supported differently across browsers as it makes some use of CSS 3 selectors, and when it comes to warnings for images, at least Internet Explorer might display errors that must not necessarily be there. To get the most of the QA style sheet test the respective pages with recent releases of Firefox, Safari, Chrome, or Opera.

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

The style sheet is somewhat unmaintained (as of January 17, 2018). [Contributions welcome.](https://github.com/j9t/qa-style-sheet/issues/new)