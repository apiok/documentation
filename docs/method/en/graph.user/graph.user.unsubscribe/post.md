graph.user.unsubscribe

$description
Unsubscribe from new chat events' messages

$payload


$additional
**Example request**

{% format_code https://api.ok.ru/graph/me/unsubscribe?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**POST-payload example**

{% highlight json %}
{
  "url": "http://sample.com/webhook.php"
}
{% endhighlight %}

**Response**

{% highlight json %}
{
  "success": true       /* Indicates if an unsubscribe event was successfully executed */
}
{% endhighlight %}