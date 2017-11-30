search.tagContents

$description
Получить медиатопики, фоточки и видео с хэштэгами

$params#query
Тэг без #

$params#filter
Где и когда считать:

* since - дата с которой искать тэги (yyyy-MM-dd HH:mm:ss)
* until - дата до которой искать тэги (yyyy-MM-dd HH:mm:ss)
* types - типы контента в которых искать: USER_TOPIC, USER_PHOTO, USER_VIDEO, GROUP_TOPIC, GROUP_PHOTO, GROUP_VIDEO

$params#anchor
Идентификатор постраничного вывода

$params#count
Количество возвращаемых результатов

$params#fields
Список запрашиваемых полей. При реальном использовании запрашивайте только действительно необходимые поля. Это влияет на число вызовов, которые вы можете делать!

$additional
Чтобы понять какие поля можно запросить в fields ткните в FieldSets. Вам откроется список корневых сущностей для каждой из которых будет список полей. 
К примеру fields для топиков, их блоков и владельцев выглядит так: 
media_topic.id, media_topic.owner_ref, media_topic.media, media_topic.media_type, media_topic.media_url_image, media_topic.like_summary, like_summary.like_count, media_topic.media_movie_refs, media_topic.media_photo_refs, 
video.content_type,video.id,video.url_mp4,video.url_provider,
group.uid,group.shortname, group.name,group.pic_avatar,group_photo.id,group_photo.pic1024max,
user.uid,user.name,user.pic128x128,user_photo.id,user_photo.pic1024max

Обратите внимание на media_topic.owner_ref - в этом поле придет ссылка на пользователя или группу. В ответе не будет ни пользователей, ни групп т.к. вы все равно не сможете разобраться кому какой топик принадлежит.