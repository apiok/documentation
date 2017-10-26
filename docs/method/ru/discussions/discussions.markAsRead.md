discussions.markAsRead

$description
Пометить все дискуссии как прочитанные

$params#version
Шорткат для поддерживаемого множества типов дискуссий.  
Например, android.1 или ios.1 будет мапиться в соответствии настройками PMS в список DiscussionType.  
Выполнение метода должно делать прочитанными только те типы дискуссий, которые могут быть отображены на этой версии приложения.

$additional
Для корректной работы во всех нижеперечисленных методах, используемых приложением, значение параметра version должно совпадать:
{% replace_method events.get %}, {% replace_method discussions.getList %}, {% replace_method discussions.markAsRead %}, {% replace_method discussions.getDiscussionsNews %}.