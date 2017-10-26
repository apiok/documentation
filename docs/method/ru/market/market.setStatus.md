market.setStatus

$description
Установить статус товара

$params#product_id
Идентификатор товара

$params#product_status
Статус товара

$additional
Для групп и для публичных страниц предусмотрен различный flow продуктовых статусов.

**Возможные переходы по статусам товаров (для групп)**

|Текущий статус		|Список статусов, в которые возможно перевести|
|-----------|-------|
|ACTIVE	|SOLD, CLOSED		|
|CLOSED		|ACTIVE |
|AUTO_CLOSED		|ACTIVE		|
|SOLD		|ACTIVE		|

**Возможные переходы по статусам товаров (для публичных страниц)**

|Текущий статус		|Список статусов, в которые возможно перевести|
|-----------|-------|
|ACTIVE	|OUT_OF_STOCK, CLOSED	|
|CLOSED		|ACTIVE |
|AUTO_CLOSED		|ACTIVE		|
|OUT_OF_STOCK		|ACTIVE		|