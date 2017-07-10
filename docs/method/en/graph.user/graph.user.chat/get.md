graph.user.chat

$description
Get chat information by ID

$params#chat:id
Chat ID in chat:id format

$additional
By this method you can acquire information about specific chat by it's ID.

ID can be specified either as a PATH parameter or GET parameter

**Request example**

Chat ID specified as a PATH parameter
{% format_code https://api.ok.ru/graph/me/chat/chat:C3ecb9d02a600?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

Chat Id specified as a GET parameter
{% format_code https://api.ok.ru/graph/me/chat?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE&chat_id=chat:C3ecb9d02a600 %}

**Response**

{% highlight json %}
{
   "type":"GROUP_CHAT",                                     /* chat type [GROUP_CHAT, DIALOG, CHAT] */
   "status":"ACTIVE",                                       /* User status for this specific chat [ACTIVE, LEFT, REMOVED] */
   "title":"Some chat title",                               /* Chat title */
   "icon":{"url":"https://st.mycdn.me/res/i/ok_logo.png"}   /* Chat icon in PNG or JPG format */
   "participants":{                                         /* Map of chat participants */
      "user:123456789012":1498581292941                     /* Key: user ID in a user:ID format, value: user's last action time as a timestamp */
   },                                       
   "lastEventTime":1498581292941,                           /* Last chat event (new message or chat event) as a timestamp */
   "chat_id":"chat:C3ecb9d02a600",                          /* Chat ID in a chat:id format */
   "owner_id":"user:123456789012",                          /* Chat owner ID in a user:id format */
   "group_id":"group:12345678901234"                        /* Group chat owner ID in a group:id format */
}
{% endhighlight %}