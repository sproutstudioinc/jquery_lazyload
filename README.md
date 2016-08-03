# Lazy Load Plugin for jQuery
# SPROUT STUDIO FORK by @mcuznz

Lazy Load delays loading of images in long web pages. Images outside of viewport wont be loaded before user scrolls to them. This is opposite of image preloading.

Using Lazy Load on long web pages containing many large images makes the page load faster. Browser will be in ready state after loading visible images. In some cases it can also help to reduce server load.

Lazy Load is inspired by [YUI ImageLoader](http://developer.yahoo.com/yui/imageloader/) Utility by Matt Mlinac.

This fork adds the following options:

- `queue_length` - specifies a maximum number of images to load simultaneously. If you're scrolling past a large number of images, the queue prevents every image from triggering instantly as it passes the viewport.  This means that if you're quickly scrolling to the bottom of a large list of images, only a handful will initially load at the top and as you scroll by, and the bulk will be loaded where you stop scrolling.  This can be crucial for providing a responsive experience with longer image galleries.  Lazy Load will operate as usual if this parameter is not set, or is set to 0.
- `loaded_class` - a CSS class to add to each image upon load, to indicate that it has in fact been loaded.
- `unbind_on_complete` - if the Lazy Load update method is called and the set of images is empty (due to either being initialized on an empty set, or all images having been loaded) the event listener is unbound.
- `event_container` - allows listening for the update event to a different element than `.lazyload()` is instantiated on.  For example, if you have `$('#container img.lazyload').lazyload()`, you may want to just assign a single event listener to the `#container` element instead.


## How to Use?

Lazy Load depends on jQuery. Include them both in end of your HTML code:

```html
<script src="jquery.js" type="text/javascript"></script>
<script src="jquery.lazyload.js" type="text/javascript"></script>
```

You must alter your HTML code. URL of the real image must be put into data-original attribute. It is good idea to give Lazy Loaded image a specific class. This way you can easily control which images plugin is binded to. Note that you should have width and height attributes in your image tag.

```html
<img class="lazy" data-original="img/example.jpg" width="640" height="480">
```

then in your code do:

```js
$("img.lazy").lazyload();
```

This causes all images of class lazy to be lazy loaded.

More information on [Lazy Load](http://www.appelsiini.net/projects/lazyload) project page.

## Install

You can install with [bower](http://bower.io/) or [npm](https://www.npmjs.com/).


```sh
$ bower install jquery.lazyload
$ npm install jquery-lazyload
```


# License

All code licensed under the [MIT License](http://www.opensource.org/licenses/mit-license.php). All images licensed under [Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/deed.en_US). In other words you are basically free to do whatever you want. Just don't remove my name from the source.
