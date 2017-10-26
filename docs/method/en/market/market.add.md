market.add

$description
Add an product.

$params#gid
Group ID

$params#type
Product type:

* GROUP_PRODUCT - product
* GROUP_SUGGESTED - suggested product (for group admin moderation).

$params#attachment
Json-formatted product content

$params#catalog_ids
Catalogs ids to add the product

$params#devices
Posting platform

$additional
Requires **strict** mediablock order in an attachment field - title(text), description(text, optional), photo (optional), product specific info. One of description or photos must be defined. Example:
{% highlight json %}
{"media":[
	{"type":"text","text":"Название товара"},
	{"type":"text","text":"Описание товара"},
	{
	    "type": "photo",
	    "list": [
	        {"id": "photoToken1"}, 
	        {"id": "photoToken2"}, 
	        {"existing_photo_id": "1234", "group": true}
	    ]
	},
	{"type":"product","price":1000,"lifetime": 30}
]}
{% endhighlight %}

Default currency is russian ruble. Default lifetime is 30 days. It is possible to specify others: USD, KZT, UAH, GEL, UZS, KGS, AZN, USD, EUR. Example with 10$ price:
{% highlight json %}
{"type":"product","price": 10, "currency": "USD", "lifetime": 30}
{% endhighlight %}


Photo uploading is similar with mediatopic. It also does **not require** commit invoking.