graph.user.info

$description
Acquire information about current Graph API token

$additional
Method allows you to get additional information about current Graph API token, i.e. token's linked group

**Request example**

{% format_code https://api.ok.ru/graph/me/info/?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**Response example**

For group token (Bot API token):
{% highlight json %}
{
  "name": "group name",
  "group_id": "group:123456789012345"
}
{% endhighlight %}