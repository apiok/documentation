graph.user.messages

$description
Get chat messages by chat ID

$params#chat:id
Chat ID in a chat:id format

$params#from
Timestamp of the latest created message

$params#to
Timestamp of the first created message

$params#count
Amount of messages to return

$additional
It must be noted tha messages are sorted by time of their creation in descending order. Therefore *from* parameter 
must be greater than *to* parameter.

Messages from a specific chat can be acquired via this method and chat ID can be set as a PATH parameter or as a GET=parameter.

**Request example**

Chat ID as a PATH parameter
{% format_code https://api.ok.ru/graph/me/messages/chat:C3ecb9d02a600?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE&from=1498581292941&to=1498577000197&count=2 %}

Chat Id as a GET parameter
{% format_code https://api.ok.ru/graph/me/messages?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE&chat_id=chat:C3ecb9d02a600&from=1498581292941&to=1498577000197&count=2 %}

**Response**

{% highlight json %}
{
  "messages": [                                             /* Array of messages in chat */
    {
      "sender": {                                           /* Message sender info */
        "name": "John Smith",                               /* Sender's first name and last name */
        "user_id": "user:123456789012"                      /* User ID in a user:id format */
      },
      "recipient": {                                        /* Message receiver info (chat, group or user) */ 
        "chat_id": "chat:C3ecb9d02a600"                     /* Chat ID (chat:id) or user ID (user:id) */
      },
      "message": {                                          /* Message info */
        "text": "text",                                     /* Message text */
        "seq": 98211023614189660,                           /* Message incrementing sequence number */
        "mid": "mid:C3ecb9d02a600.15cea67d78d2059"          /* Message ID in a mid:id format */
      },
      "timestamp": 1498581292941                            /* Message creation time (timestamp) */
    },
    {
      "sender": {
        "name": "John Smith",
        "user_id": "user:123456789012"
      },
      "recipient": {
        "chat_id": "chat:C3ecb9d02a600"
      },
      "message": {
        "text": "https://ya.ru/",
        "seq": 98211018056672380,
        "attachments": [                                    /* Array of attachments */            
          {
            "type": "SHARE",                                /* Attachment type [VIDEO, AUDIO, SHARE, IMAGE] */
            "payload": {                                    /* type-specific attachment data. Atm it is the same for all types */
              "url": "https://ya.ru/"                       /* Resource URL */
            }
          }
        ],
        "mid": "mid:C3ecb9d02a600.15cea668c4c2481"
      },
      "timestamp": 1498581208140
    }
  ]
}
{% endhighlight %}

**Attachment types**

Following attachments types can be a part of message:

* type=IMAGE - image attachment;
* type=VIDEO - video attachment (OK video or a link to i.e. youtube video);
* type=AUDIO - audio attachment (user recorded audio or link to a music track on OK);
* type=SHARE - a link share that was processed by our grabber.