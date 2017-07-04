search.tagSearch

$description
Search for #tags with given character sequence (3 characters minimum!). Tags are sorted by their popularity.

$params#query
Character sequence (3 characters minimum!)

$params#filter
Filters determining where and when to look:

* since - date filter (yyyy-MM-dd HH:mm:ss)
* until - date filter (yyyy-MM-dd HH:mm:ss)
* types - content types to look into: USER_TOPIC, USER_PHOTO, USER_VIDEO, GROUP_TOPIC, GROUP_PHOTO, GROUP_VIDEO

$params#count
Number of tags to return

$additional
Response example:

{% highlight json %}
{
    "tags":[
        {
            "query":"ok",
            "all":4,
            "userTopics":0,
            "userPhotos":0,
            "userVideos":0,
            "groupTopics":4,
            "groupPhotos":0,
            "groupVideos":0
        },{
            "query":"apiok",
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