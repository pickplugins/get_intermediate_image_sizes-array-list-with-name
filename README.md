# get_intermediate_image_sizes array list with name

get_intermediate_image_sizes() only return the name of available image size, but sometime we will need the array with title to generate input select, radio fields 

```php

function intermediate_image_sizes_array(){


	$get_intermediate_image_sizes =  get_intermediate_image_sizes();
	$get_intermediate_image_sizes = array_merge($get_intermediate_image_sizes,array('full'));

	$all_sizes = array();

	foreach($get_intermediate_image_sizes as $size_key){

		$size_key_title = str_replace('_', ' ',$size_key);
		$size_key_title = str_replace('-', ' ',$size_key_title);
		$all_sizes[$size_key] = ucfirst($size_key_title);
	}

	return $all_sizes;


}

```


##Output
the function will return like this.

```php
array (
  'thumbnail' => 'Thumbnail',
  'medium' => 'Medium',
  'medium_large' => 'Medium large',
  'large' => 'Large',
  'post-thumbnail' => 'Post thumbnail',
  'woocommerce_thumbnail' => 'Woocommerce thumbnail',
  'woocommerce_single' => 'Woocommerce single',
  'woocommerce_thumbnail_2x' => 'Woocommerce thumbnail 2x',
  'shop_thumbnail' => 'Shop thumbnail',
  'shop_catalog' => 'Shop catalog',
  'shop_single' => 'Shop single',
  'full' => 'Full',
)
```

So you can use this array using loop to generate input field for select, radio and etc