mediatopic.getRepublishedTopic

$description
Получение id топика после перепубликации (например, после прохождения модерации или публикации отложенного поста)

$params#topic_id
id старого топика до перепубликации

$additional
Работает в {% replace_method batch.execute %} с супплаером **mediatopic.getRepublishedTopic.mid**:

{% highlight json %}
[{
    "method": "mediatopic.getRepublishedTopic",
    "params": {
        "topic_id": "10244259905713"
    }
}, {
    "method": "mediatopic.getByIds",
    "params": {
        "topic_ids": {
            "supplier": "mediatopic.getRepublishedTopic.mid"
        },
        "fields": "media_topic.*"
    }
}]
{% endhighlight %}