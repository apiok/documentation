graph.user.chat

$description
Получение информации о чате по его ID

$params#chat:id
ID чата в формате chat:id

$additional
С помощью метода можно получить информацию об определенном чате по ID.

ID может указываться либо в PATH, либо в виде GET-параметра.

**Пример запроса**

С указанием ID чата в PATH
{% format_code https://api.ok.ru/graph/me/chat/chat:C3ecb9d02a600?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

С указанием ID чата в GET-параметре
{% format_code https://api.ok.ru/graph/me/chat?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE&chat_id=chat:C3ecb9d02a600 %}

**Ответ**

{% highlight json %}
{
   "type":"GROUP_CHAT",                                     /* тип чата [GROUP_CHAT, DIALOG, CHAT] */
   "status":"ACTIVE",                                       /* Статус пользователя относительно чата [ACTIVE, LEFT, REMOVED] */
   "title":"Some chat title",                               /* Название чата */
   "icon":{"url":"https://st.mycdn.me/res/i/ok_logo.png"}   /* URL иконки чата в формате jpg или png */
   "participants":{                                         /* Map пользователей-участников чата */
      "user:123456789012":1498581292941                     /* Key: ID пользователя в формате user:ID, value: время последнего действия в чате */
   },                                       
   "lastEventTime":1498581292941,                           /* Время последнего изменения чата или сообщений в этом чате */
   "chat_id":"chat:C3ecb9d02a600",                          /* ID чата в формате chat:id */
   "owner_id":"user:123456789012",                          /* ID пользователя-владельца чата в формате user:id */
   "group_id":"group:12345678901234"                        /* ID группы-владельца чата в формате group:id */
}
{% endhighlight %}