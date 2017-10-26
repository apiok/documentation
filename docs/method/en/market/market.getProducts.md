market.getProducts

$description
Get portlet on the main group page

$params#gid
Group id

$params#tab
* PRODUCTS - all products of group
* ON_MODERATION - products on moderation (for user - user's own, for admin - all products on moderation of the group)
* OWN - user's own products, including on moderation ones

$params#anchor
Anchor for paging

$params#direction
Direction for paging

$params#count
Count for paging

$params#fields
Requesting fields

$additional
Product can be represented as:

|Representation		|Methods|
|-----------|-------|
|mediatopic with text blocks	|all methods from [mediatopic](/dev/methods/rest/market/)	|
|mediatopic with product block		|method {% replace_method market.getByIds %} and all methods from [mediatopic](/dev/methods/rest/market/) with features = "PRODUCT.1" |
|{% replace_type ShortProductBean %}	|method {% replace_method market.getProducts %} and {% replace_method search.quick %} with features = "SHORT_PRODUCT.1"|