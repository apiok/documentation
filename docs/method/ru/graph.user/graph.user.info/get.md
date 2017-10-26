graph.user.info

$description
Получение информации о текущем токене Graph API

$additional
Метод позволяет получить информацию о том, кому принадлежит текущий токен Graph API, который используется в рамках вызова метода.

**Пример запроса**

{% format_code https://api.ok.ru/graph/me/info/?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**Пример ответа**

Для токена, полученного в группе (токен Bot API):
{% highlight json %}
{
  "name": "название группы",
  "group_id": "group:123456789012345"
}
{% endhighlight %}