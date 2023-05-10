# Which is better?

## Option A:
```
<?php foreach ($terms as $term): ?>
    <?php if($term->slug == "featured"): ?>
        <li class="product-filter-item" data-product-filter="<?php echo esc_attr( $term->slug ); ?>">
            <a href="javascript:void(0)" data-slug="<?php echo $term->slug; ?>" class="btn btn-rounded get-by-location">
                <?php echo $term->name; ?>
            </a>
        </li>
    <?php else: ?>
        <li class="product-filter-item" data-product-filter="<?php echo esc_attr( $term->slug ); ?>">
            <a href="javascript:void(0)" data-slug="<?php echo $term->slug; ?>" class="btn btn-rounded get-by-location">
                <?php echo $term->name; ?>
            </a>
        </li>
    <?php endif; ?>
<?php endforeach; ?>
```

## Option B:
```
<ul class="locations-list test">
    <?php
     foreach ($terms as $term) { 
        if($term->slug == "featured" ) {?>
         
            <li class="product-filter-item" data-product-filter="<?php echo esc_attr( $term->slug ); ?>"><a href="javascript:void(0)" data-slug="<?php echo $term->slug; ?>" class="btn btn-rounded get-by-location active"><?php echo $term->name; ?></a></li>
        <?php } ?>
    <?php }
    
    foreach ($terms as $term) { 
        if($term->slug !== "featured" ) { ?>
            <li class="product-filter-item" data-product-filter="<?php echo esc_attr( $term->slug ); ?>"><a href="javascript:void(0)" data-slug="<?php echo $term->slug; ?>" class="btn btn-rounded get-by-location"><?php echo $term->name; ?></a></li>
        <?php }
    }?>
</ul>
```