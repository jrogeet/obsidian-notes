![[Pasted image 20230215082954.png]]

Max-width - 


-   `%` is relative to the dimensions of the parent - so this is useful for creating sizing systems that can be inherited - e.g. a cascade of nested elements whose heights are all relative to each other - so you only need a single ancestor whose dimensions are specific, and the descendants will resize based on that element.
    
-   `vw` and `vh` are relative to the dimensions of the entire viewport - so this is useful for 'escaping' the relative resizing of `%` - when you're 20 elements deep and just need to know the width or height of the screen again (note: `100vw` excludes the vertical scrollbar, and `100vh` excludes the horizontal scrollbar and bookmarks bar, so both may be slightly larger than you expect)
    
-   `em` is relative to the `font-size` of the parent (ie. the inherited `font-size` of the current element) - like `%` this is useful for creating sizing systems based off of the `font-size` of a single ancestor; for example to implement [the golden ratio](https://www.google.com/search?q=golden+ratio&oq=golden+ratio&aqs=chrome..69i57.1556j0j4&sourceid=chrome&ie=UTF-8), the font-size of an ancestor could be `1rem`; body text is `1em`, subheadings are `1.618em`, and headings are `2.618em` - changing the font-size of the ancestor from `1rem` to `2rem` will now resize all of the text with the correct proportions. Nearly everything should be implemented with `em` in this way, and if you're in doubt as to which element sizes are connected to which pieces of text then just ask the designer you're working with - they'll be so happy you asked.
    
-   `rem`, like, `vw` and `vh`, is a way to 'escape' the relative resizing of `em`, and is relative to the `font-size` specified in your `html` tag - when you're 20 elements deep and you encounter something that doesn't need to scale as part of a larger system, and just need it to be a 'fixed' size as part of the document, then you can specify a `font-size` in `rem` and it will return to the constant of the root.
    
-   `vmin` is a comparative unit - taking whichever is the smaller between `vw` and `vh` - so think of the use-case for those units, and add on-top of that an 'area' query. This is useful for when you have something that always needs to be fully in-area- e.g. a `100vmin` x `100vmin` box will be a square that always fits inside the window; think of it like 'contain' when setting your desktop background.
    
-   `vmax` is the opposite of `vmin` - it will take whichever is the _larger_ between `vw` and `vh` - this is useful for when you have something that always needs to at least _fill_ an area; think of it like 'cover' when setting your desktop background.
    
-   `1ch` is the width of the character `0` in the current font - so while `1em` is a good way to describe the _height_ of a line of text, using `ch` can be a good way to describe the _width_ of a text string - e.g. the world `hello` in a monospace font will be exactly `5ch` wide and `1em` tall.
    
-   `px` is an absolute unit equal to the scaled dimensions of the user's current resolution (ie. it takes into account system UI scaling and browser UI scaling) when working for the web, it's the unit you should use last when all other units aren't appropriate, or when you explicitly want to describe something at a fixed size - for example setting a `max-width` of an image to that image's natural width in pixels, so that it never grows beyond its natural size.
    
-   `cm`, `mm`, `in`, `pc`, and `pt` are all physical sizes and should only be used when styling your site for print - while the web uses `px` as its 'base' sizing unit, for print it often makes more sense to use `mm` or `pt` - just make sure to whack it into an `@media(print){ ... }` media-query.