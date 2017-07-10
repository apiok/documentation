graph.user.chats

$description
Get information about all owned or participated chats

$params#marker
Paging marker<br/>
Must be empty in a first request. Value for further requests can be get in a previous API response

$params#count
Number of chats to be returned<br/>
Value from 1 to 100

$additional
Method is user to get information about all chats and dialogs user or group has participated in.
Chat are sorted based on a last activity time. Chats with the most recent activities come first.

Since the number of chats can exceed the maximum number of chats returned by method the *marker* parameter should be used
to get all chats using paging feature of the method.

In each consequent request *marker* parameter can be specified based on a previous API response.
If *marker* is not present in a response it means you've reached the end of chats' list.

It is recommended to use /me/chat method if chat Id is already known.

**Request example**

{% format_code https://api.ok.ru/graph/me/chats?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE&count=1 %}

**Response**

{% highlight json %}
{
  "chats": [                                                    /* Array of chat objects. Same as in method me/chat */
    {
      "type": "GROUP_CHAT",                                     /* chat type [GROUP_CHAT, DIALOG, CHAT] */
      "status": "ACTIVE",                                       /* User status for this specific chat [ACTIVE, LEFT, REMOVED] */
      "title": "Some chat title",                               /* Chat title */
      "icon":{"url":"https://st.mycdn.me/res/i/ok_logo.png"},   /* Chat icon in PNG or JPG format */
      "participants": {                                         /* Map of chat participants */
        "user:123456789012": 1498581292941                      /* Key: user ID in a user:ID format, value: user's last action time as a timestamp */
      },
      "lastEventTime": 1498581292941,                           /* Last chat event (new message or chat event) as a timestamp */
      "chat_id": "chat:C3ecb9d02a600",                          /* Chat ID in a chat:id format */
      "owner_id": "user:123456789012",                          /* Chat owner ID in a user:id format */
      "group_id": "group:12345678901234"                        /* Group chat owner ID in a group:id format */
    }
  ],
  "marker": "LTE0OTcyNDMzNTYzMzM6LTE0OTcyNDMzNTYzMzM="          /* Paging marker */
}
{% endhighlight %}