graph.user.subscriptions

$description
List of Webhook subscriptions

$additional
**Example request**

{% format_code https://api.ok.ru/graph/me/subscriptions?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**Response**

{% highlight json %}
{
  "subscriptions": [                                    /* Array of Webhooks API sends messages to*/
    {
      "time": 1498577751487,                            /* Time of a subscription event */
      "url": "https://sample.com/webhook.php"           /* Webhook URL */
    }
  ]
}
{% endhighlight %}