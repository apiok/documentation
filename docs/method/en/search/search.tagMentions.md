search.tagMentions

$description
Get number of tag mentions. This counts include private records.

$params#query
Tag without #

$params#filter
Where and when to count:

* since - date filter (yyyy-MM-dd HH:mm:ss)
* until - date filter (yyyy-MM-dd HH:mm:ss)
* types - content types to look into: USER_TOPIC, USER_PHOTO, USER_VIDEO, GROUP_TOPIC, GROUP_PHOTO, GROUP_VIDEO

$additional
Response example: 

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