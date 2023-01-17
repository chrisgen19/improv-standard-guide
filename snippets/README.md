<h1 align="center">
<br>
    <img src="https://cdn.myimprov.com/wp-content/uploads/20220513155747/myimprov-logo-2022.png" alt="Improv Checklist" width="220">
    <br>
    <br>
    Improv Code Snippets
  <br>
</h1>


## Here's a sample code that you can use in WordPress to list all the page templates and the pages that use them:


```php
<?php
// Get all page templates
$templates = get_page_templates();

// Loop through the templates
foreach ( $templates as $template_name => $template_file ) {
    // Get the pages that use the template
    $pages = get_pages( array(
        'meta_key' => '_wp_page_template',
        'meta_value' => $template_file
    ) );

    // Print the template name and file
    echo '<h2>' . $template_name . ' (' . $template_file . ')</h2>';

    // Print the pages that use the template
    echo '<ul>';
    foreach ( $pages as $page ) {
        echo '<li><a href="' . get_permalink( $page->ID ) . '">' . $page->post_title . '</a></li>';
    }
    echo '</ul>';
}
?>
```

This code uses the get_page_templates() function to get all the page templates available in the theme, and the get_pages() function to get the pages that use a specific template. It then loops through the templates and prints the template name and file, followed by a list of the pages that use that template.

You can use this code in a custom plugin or in your theme's functions.php file. Keep in mind that you should test the code in a local environment or a test site before using it on a live site. Also, you may want to style the output of the code to match your website design.

## How to center object in CSS using grid

It's worth to note that, you can also use the place-items shorthand property to center items both horizontally and vertically at once.

```css
.grid-container {
  display: grid;
  place-items: center;
}
```

## Simple Hero Slider

```html
<div class="hero-slider">
  <img src="image-1.jpg" alt="slide 1" class="hero-slide active">
  <img src="image-2.jpg" alt="slide 2" class="hero-slide">
  <img src="image-3.jpg" alt="slide 3" class="hero-slide">
</div>
```

```css
.hero-slider {
  position: relative;
  width: 100%;
  height: 500px; /* Set the desired height for your slider */
}

.hero-slide {
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0;
  transition: opacity 1s;
}

.hero-slide.active {
  opacity: 1;
}
```

```js
const heroSlider = document.querySelector('.hero-slider');
const heroSlides = document.querySelectorAll('.hero-slide');
let currentSlide = 0;

function showNextSlide() {
  heroSlides[currentSlide].classList.remove('active');
  currentSlide = (currentSlide + 1) % heroSlides.length;
  heroSlides[currentSlide].classList.add('active');
}

setInterval(showNextSlide, 5000); /* This will change the slide every 5 seconds */
```

This code will create a simple hero slider with 3 images and a fixed height. The images will transition every 5 seconds. You can change the time interval as per your requirement.

You may need to adjust the styling as per your design requirement.