<h1 align="center">
<br>
    <img src="https://cdn.myimprov.com/wp-content/uploads/20220513155747/myimprov-logo-2022.png" alt="Improv Checklist" width="220">
    <br>
    <br>
    Improv Responsive Development Best Practice
  <br>
</h1>

## Table of Contents
<details>
  <summary>
    <a href="#1-images">1. Images</a>
  </summary>

&emsp;&emsp;[1.1 Responsive Image](#11-responsive-image)</br>
</details>

## 1. Images

### 1.1 Responsive Image

You can create a responsive image using the img element and the CSS max-width property. The max-width property allows you to set a maximum width for an element, so that it will scale down to fit smaller screens. Here is an example:

```html
<img src="image.jpg" alt="My image" class="responsive-image">
```

```css
.responsive-image {
  max-width: 100%; /* image will scale down to fit the screen */
  height: auto; /* maintain aspect ratio */
}
```

This will create an image that scales down to fit the screen, while maintaining its aspect ratio. The max-width property is set to 100%, so the image will never be wider than the screen. The height property is set to auto so that the aspect ratio is maintained when the width changes.

You can also use the object-fit property to control how the image is resized within the box.

```css
.responsive-image {
  max-width: 100%;
  height: auto;
  object-fit: cover; /* Scale the image to completely fill the containing element */
}
```

You can also use the srcset attribute to provide different versions of the image at different sizes, and the browser will choose the best one for the device.

```html
<img src="image-small.jpg" alt="My image" class="responsive-image"
  srcset="image-small.jpg 400w, image-medium.jpg 800w, image-large.jpg 1200w"
  sizes="(max-width: 600px) 400px, (max-width: 1200px) 800px, 1200px">
```

