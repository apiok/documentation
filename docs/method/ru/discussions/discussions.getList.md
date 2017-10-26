discussions.getList

$description
Получение списка дискуссий

$params#types
Типы объектов дискуссии, разделенные запятой

$params#version
Шорткат для поддерживаемого множества типов дискуссий.  
Например, android.1 или ios.1 будет мапиться в соответствии настройками PMS в список DiscussionType.  
Нужен для того чтобы показывать "Скрыть все" только в случае когда есть непрочитанные дискусии которые могут быть отображенны на этом устройстве.

$params#category
Категория объекта дискуссии, по которой фильтруются результаты

$params#anchor
Идентификатор постраничного вывода

$params#direction
Направление постраничного вывода

$params#count
Количество возвращаемых результатов

$params#fields
Список запрашиваемых полей

$params#fieldset
Задаёт список запрашиваемых полей в виде названия набора полей, определённого в настройках сервера

$params#locale
Язык

$params#features
Фичи, которые поддерживает клиент

$additional
Для корректной работы во всех нижеперечисленных методах, используемых приложением, значение параметра version должно совпадать:
{% replace_method events.get %}, {% replace_method discussions.getList %}, {% replace_method discussions.markAsRead %}, {% replace_method discussions.getDiscussionsNews %}.