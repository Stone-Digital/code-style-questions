# Which is better?

## Option A:
```
<?php 
   function get_categories_name_for_class( ) {
        $separator = ' ';
        $cat_name_as_class = '';
        $post_type = get_post_type(get_the_ID());   
        $taxonomies = get_object_taxonomies($post_type);
        $taxonomy_slugs = wp_get_object_terms(get_the_ID(), $taxonomies,  array("fields" => "slugs"));
        
            foreach($taxonomy_slugs as $tax_slug) :            
                $cat_name_as_class .= $tax_slug . $separator ; 
            endforeach;
            return trim( $cat_name_as_class, $separator );
         
    }

>
```

## Option B:
```
<?php 
function get_categories_name_for_class( ) {
    $separator = ' ';
    $cat_name_as_class = '';
    $post_type = get_post_type(get_the_ID());   
    $taxonomies = get_object_taxonomies($post_type);
    $taxonomy_slugs = wp_get_object_terms(get_the_ID(), $taxonomies,  array("fields" => "slugs"));
    foreach($taxonomy_slugs as $tax_slug) {
        $cat_name_as_class .= $tax_slug . $separator ; 
    }         
    return trim( $cat_name_as_class, $separator );
}
>
```