# Core Web Vitals Tips

Tips & tricks to minimize site speed & cwv issues

### General images
* Always set width and height attributes on all img tags, including svgs
* Inline lcp image for best result. If not, add a preload link for lcp image
* Avoid png format for bitmap photos
* Avoid using css classes to hide images/videos on mobile
- Example:
```html
<!-- Very bad -->
<img src="/huuuuge-desktop-image.jpeg" 
    width="1920" height="700" 
    decoding="async" alt="alt text" 
    class="hide-for-small" 
/>

<!-- Sort of good, using data svg to avoid larger image load on mobile -->
<!-- [Reference](https://swimburger.net/blog/web/web-performance-prevent-wasteful-hidden-image-requests#solution-code) -->
<picture>
    <source srcset="data:image/gif;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs=" media="(max-width: 640px)"> 
    <img src="/huuuuge-desktop-image.jpeg"
        width="1920" height="700"
        decoding="async" loading="lazy"
        alt="alt text"
        class=""
    />
</picture>
```

### Main message images
* Inline <img> for main message instead of using background images when possible

### Preload LCP
* Set up preload for your LCP and always check if an existing one needs to be updated when main message changes
- Example:
```html
<!-- preloads for main message image -->
<?php if ($thePage == "index") { ?>
<link rel="preload" fetchpriority="high" href="https://cdn.treehouseinternetgroup.com/cdn-cgi/image/format=auto,quality=70/cms_images/606/mm-500.jpeg" as="image" media="(max-width: 499px)">
<link rel="preload" fetchpriority="high" href="https://cdn.treehouseinternetgroup.com/cdn-cgi/image/format=auto,quality=70/cms_images/606/mm-800.jpeg" as="image" media="(min-width: 500px) and (max-width: 799px)">
<link rel="preload" fetchpriority="high" href="https://cdn.treehouseinternetgroup.com/cdn-cgi/image/format=auto,quality=70/cms_images/606/mm-1600.jpeg" as="image" media="(min-width: 800px)">
<?php } ?>
```

### Lazyloading
* Don't lazy load above the fold images
* To lazyload on mobile only you can use the following php snippet
```html
<img src="/big-desktop-image.jpeg" 
    width="300" 
    height="200" 
    decoding="async" 
    alt="alt text" 
    class="" 
    <?php if($isMobile) echo 'loading="lazy"' ?>
/>
```
