users.setSettings

$description
Сохраняет настройки в профиле пользователя на портале

$params#smsNotifAdd
Список типов событий, которые должны быть добавлены в список SMS-уведомлений

$params#smsNotifRemove
Список типов событий, которые должны быть удалены из списка SMS-уведомлений

$params#smsNotifStartTime
Время начала в формате «ЧЧ:ММ», когда пользователь разрешает доставку SMS-уведомлений

$params#smsNotifEndTime
Время окончания в формате «ЧЧ:ММ», когда пользователь разрешает доставку SMS-уведомлений

$additional
Перечень возможных типов событий:

|Тип события|
|-----------|
|NewMarks|
|NewPresents|
|NewMessages|
|NewAltGroupInvitations|
|AltGroupJoiningAccepted|
|AltGroupModeratorInvitations|
|NewPhotoPins|
|NewForumMessages|
|NewPhotoComments|
|NewFriendConfirmations|
|NewStatusComments|
|AppInvitations|
|FriendRecommendations|
|FriendBirthdays|