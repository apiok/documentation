stream.delete

$description
Метод удаляет событие из ленты пользователя

$params#delete_id
Идентификатор элемента ленты для удаления. Имеется только у элементов своей ленты.

Параметр delete_id берётся из элемента feed.delete_id метода отображения ленты {% replace_method stream.get %}

$params#banner_id
Идентификатор баннера для удаления. Если указан, то этот и все другие баннеры от того же рекламодателя будет скрыты для пользователя на 1 год.

$params#banner_opt
Json map дополнительных параметров, пробрасываемых в неизменном виде к РБ (см. [Протокол взаимодействия S2S с мобильными ОК](https://confluence.mail.ru/pages/viewpage.action?pageId=43977070)). Игнорируется, если не указан banner_id.

$params#delete_ref_id


$additional
