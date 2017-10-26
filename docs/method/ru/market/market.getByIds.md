market.getByIds

$description
Получение товаров

$params#product_ids
Идентификаторы товаров

$params#fields
Список запрашиваемых полей

$additional
Товар может быть представлен в трех различных форматах:

|Представление		|Методы|
|-----------|-------|
|медиатопик с текстовыми блоками	|все методы раздела [mediatopic](/dev/methods/rest/market/)	|
|медиатопик с блоком product		|метод {% replace_method market.getByIds %} и все методы раздела [mediatopic](/dev/methods/rest/market/) с features = "PRODUCT.1" |
|{% replace_type ShortProductBean %}	|метод {% replace_method market.getProducts %} и {% replace_method search.quick %} c features = "SHORT_PRODUCT.1"|