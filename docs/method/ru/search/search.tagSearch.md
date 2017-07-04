search.tagSearch

$description
Найти #тэги в которых есть указанная последовательность символов (миниум 3 символа). Найденые тэги сортируются по популярности.

$params#query
Последовательность символов (миниум 3 символа)

$params#filter
Фильтры для отбора тэгов:

* since - дата с которой искать тэги (yyyy-MM-dd HH:mm:ss)
* until - дата до которой искать тэги (yyyy-MM-dd HH:mm:ss)
* types - типы контента в которых искать: USER_TOPIC, USER_PHOTO, USER_VIDEO, GROUP_TOPIC, GROUP_PHOTO, GROUP_VIDEO

$params#count
Количество возвращаемых результатов.

$additional
Пример ответа:

{% highlight json %}
{
    "tags":[
        {
            "query":"всеок",
            "all":4,
            "userTopics":0,
            "userPhotos":0,
            "userVideos":0,
            "groupTopics":4,
            "groupPhotos":0,
            "groupVideos":0
        },{
            "query":"апиок",
            "all":2,
            "userTopics":2,
            "userPhotos":0,
            "userVideos":0,
            "groupTopics":0,
            "groupPhotos":0,
            "groupVideos":0
        }
    ],
    "count":3
}
{% endhighlight %}