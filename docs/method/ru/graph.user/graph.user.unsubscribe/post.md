graph.user.unsubscribe

$description
Отписка от получения сообщений через Webhook

$payload
{% highlight json %}
{
    "url": String  /* http: или https: URL, который надо убрать из списка на получния событий о сообщениях в чатах */
}
{% endhighlight %}

$additional
**Пример запроса**

{% format_code https://api.ok.ru/graph/me/unsubscribe?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**Пример POST-payload**

{% highlight json %}
{
  "url": "http://sample.com/webhook.php"
}
{% endhighlight %}

**Ответ**

{% highlight json %}
{
  "success": true       /* Индикатор того, что отписка произошла успешно */
}
{% endhighlight %}