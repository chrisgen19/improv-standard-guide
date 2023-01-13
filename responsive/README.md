<h1 align="center">
<br>
    <img src="https://cdn.myimprov.com/wp-content/uploads/20220513155747/myimprov-logo-2022.png" alt="Improv Checklist" width="220">
    <br>
    <br>
    Improv Responsive Development Best Practice
  <br>
</h1>

## Table of Contents

[1. Images](#1-images)</br>
&nbsp;&nbsp;[1.1 Responsive Image](#11-responsive-image)</br>
&nbsp;&nbsp;[1.2 Responsive Div](#12-responsive-dive)</br>
[2. Flexbox](#2-flexbox)</br>
&nbsp;&nbsp;[2.1 Flexbox Image](#21-flexbox-image)</br>
[3. Grid Layout](#2-grid-layout)</br>
&nbsp;&nbsp;[3.1 Grid Elements](#21-grid-elements)</br>

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

## 3. Grid Layout

### 3.1 Grid Elements

here is an example of how you can create a product row and column using CSS Grid:

HTML
```html
<div class="product-grid">
  <div class="product">
    <img src="product-image.jpg" alt="Product 1">
    <h3>Product 1</h3>
    <p>Product 1 Description</p>
    <button>Add to Cart</button>
  </div>
  <div class="product">
    <img src="product-image.jpg" alt="Product 2">
    <h3>Product 2</h3>
    <p>Product 2 Description</p>
    <button>Add to Cart</button>
  </div>
  <div class="product">
    <img src="product-image.jpg" alt="Product 3">
    <h3>Product 3</h3>
    <p>Product 3 Description</p>
    <button>Add to Cart</button>
  </div>
</div>
```
CSS
```css
.product-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 columns */
  grid-gap: 16px; /* 16px gap between each product */
}

.product {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}
```

To make the product grid responsive, you can use CSS media queries to change the grid-template-columns property based on the screen size. For example, you can set the grid to have one column on mobile devices, and three columns on larger screens:

```css
@media (max-width: 600px) {
  .product-grid {
    grid-template-columns: 1fr; /* 1 column on mobile devices */
  }
}

@media (min-width: 601px) {
  .product-grid {
    grid-template-columns: repeat(3, 1fr); /* 3 columns on larger screens */
  }
}
```

This media query will change the grid-template-columns property when the screen width is less than 600px. It will set the grid to have 1 column for mobile devices. For screens larger than 600px, the grid will have 3 columns.

You can also use other media query features like min-width, max-width, min-height, max-height and orientation to make it more refined.

In addition, you can use other CSS properties like flex-wrap:wrap to help with responsive behaviour.