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

```css
.grid-container {
  display: grid;
  place-items: center;
}
```