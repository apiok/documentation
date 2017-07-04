search.tagMentions

$description
Получить количество упоминаний #тэга(ов). Учитываются в т.ч. приватные записи.

$params#query
Тэг без #

$params#filter
Где и когда считать:

* since - дата с которой искать тэги (yyyy-MM-dd HH:mm:ss)
* until - дата до которой искать тэги (yyyy-MM-dd HH:mm:ss)
* types - типы контента в которых искать: USER_TOPIC, USER_PHOTO, USER_VIDEO, GROUP_TOPIC, GROUP_PHOTO, GROUP_VIDEO

$additional
Пример ответа: 

{% highlight json %}
{
    "query":"apiok",
    "all":231,
    "userTopics":11,
    "userPhotos":22,
    "userVideos":33,
    "groupTopics":44,
    "groupPhotos":55,
    "groupVideos":66
}
{% endhighlight %}