market.getProducts

$description
Получение товаров

$params#gid
Ид группы

$params#tab
* PRODUCTS - все товары внутри группы
* ON_MODERATION - товары на модерации (для участника - собственные, для администрации - товары других участников)
* OWN - товары текущего пользователя

$params#anchor
Идентификатор постраничного вывода

$params#direction
Направление постраничного вывода

$params#count
Количество возвращаемых результатов

$params#fields
Список запрашиваемых полей

$additional
Товар может быть представлен в трех различных форматах:

|Представление		|Методы|
|-----------|-------|
|медиатопик с текстовыми блоками	|все методы раздела [mediatopic](/dev/methods/rest/market/)	|
|медиатопик с блоком product		|метод {% replace_method market.getByIds %} и все методы раздела [mediatopic](/dev/methods/rest/market/) с features = "PRODUCT.1" |
|{% replace_type ShortProductBean %}	|метод {% replace_method market.getProducts %} и {% replace_method search.quick %} c features = "SHORT_PRODUCT.1"|