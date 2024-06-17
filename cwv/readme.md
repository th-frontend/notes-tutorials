# Core Web Vitals Tips

Tips & tricks to minimize site speed & cwv issues

### Preconnects/Preloads
* Always place preconnect/preloads early in <head> so they're processed sooner
- Example:
```html
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>[[title]]</title>

    <!-- preconnects -->
    <link rel="preconnect" href="https://cdn.treehouseinternetgroup.com">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <!-- preloads -->
    <link rel="preload" fetchpriority="high" href="" as="image" media="(max-width: 640px)">

    <meta name="description" content="[[description]]">
    <meta name="keywords" content="[[keywords]]">
    <meta name="ahrefs-site-verification" content="06b55c0e0b6410adb261079a7020da80954b263f5aa13211d5454e27cc1e28a6">
    <link rel="icon" href="https://cdn.treehouseinternetgroup.com/cms_images/1862/favicons.png">
    [[custom_core_v3_9x]]
    <style>[[inline_css]]</style>
    <link href="https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,300;0,400;0,700;1,400&display=swap" rel="stylesheet">
</head>
```

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
[Reference](https://swimburger.net/blog/web/web-performance-prevent-wasteful-hidden-image-requests#solution-code)
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
* For responsive background images, wrap default size in @media to avoid downloading multiple images  
- Example:
```html
<!-- this will still download the default image as well as the media queried image -->
.main-slide.slide1 { background:url('/slide-1.jpg'); }
@media screen (min-width:641px) and (max-width:1024px) {
    .main-slide.slide1 {background:url('/slide-1-md.jpg');}
}
@media screen and (max-width:640px) {
    .main-slide.slide1 { background:url('/slide-1-sm.jpg'); }
}

<!-- avoid by wrapping default image in it's own media query -->
@media screen (min-width:1025px) {
    .main-slide.slide1 { background:url('/slide-1.jpg'); }
}
@media screen (min-width:641px) and (max-width:1024px) {
    .main-slide.slide1 {background:url('/slide-1-md.jpg');}
}
@media screen and (max-width:640px) {
    .main-slide.slide1 { background:url('/slide-1-sm.jpg'); }
}
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
* To lazyload for mobile only, you can use the following php snippet
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
