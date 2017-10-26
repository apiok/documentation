market.getByIds

$description
Get products by ids

$params#product_ids
Product ids

$params#fields
Requesting fields

$additional
Product can be represented as:

|Representation		|Methods|
|-----------|-------|
|mediatopic with text blocks	|all methods from [mediatopic](/dev/methods/rest/market/)	|
|mediatopic with product block		|method {% replace_method market.getByIds %} and all methods from [mediatopic](/dev/methods/rest/market/) with features = "PRODUCT.1" |
|{% replace_type ShortProductBean %}	|method {% replace_method market.getProducts %} and {% replace_method search.quick %} with features = "SHORT_PRODUCT.1"|