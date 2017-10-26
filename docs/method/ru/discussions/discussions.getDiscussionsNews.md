discussions.getDiscussionsNews

$description
Получение информации о новостях дискуссий, на которые подписан пользователь.

$params#version
Шорткат для поддерживаемого множества типов дискуссий.  
Например, android.1 или ios.1 будет мапиться в соответствии настройками PMS в список DiscussionType.  
Нужен для того чтобы показывать "Скрыть все" только в случае когда есть непрочитанные дискусии которые могут быть отображенны на этом устройстве.

$additional
Для корректной работы во всех нижеперечисленных методах, используемых приложением, значение параметра version должно совпадать:
{% replace_method events.get %}, {% replace_method discussions.getList %}, {% replace_method discussions.markAsRead %}, {% replace_method discussions.getDiscussionsNews %}.