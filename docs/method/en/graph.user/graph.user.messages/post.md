graph.user.messages

$description
Create new messages, modify chats, dialogs and their participants

$payload


$additional
This method allows you to do following actions:

* create new chat messages;
* modify chat / dialog state;
* chat participants management;
* notify other chat participants about your actions and state.

**Request example**

{% format_code https://api.ok.ru/graph/me/messages/chat:C3ecb9d02a600?access_token=tkn18YdUJZe:CQABPOJKAKEKEKEKE %}

**Actions over chat state**

You can edit following chat data:

* chat title;
* chat logo. 

Example request to edit chat title:
{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},           /* Chat ID in a chat:id format */
  "chat_control":{
    "title":"This is our chat now"                        /* New chat title */
  }
}
{% endhighlight %}

Example request to edit chat icon:
{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},                 /* Chat ID in a chat:id format */
  "chat_control":{
    "icon":{"url":"https://and.su/tamtam/icon128.png"}          /* New icon image URL. Png or img formats only */
  }
}
{% endhighlight %}

**Participants management**

Following actions can be done with / or by chat participants:

* add new chat participant;
* remove chat participant;
* leave chat by current user

Example request to add new chat participant:

{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},         /* Chat ID in a chat:id format */
  "chat_control":{
    "add_members":[                                     /* Array of user to add */
      {"user_id":"user:123456789012"},                  /* User ID in a user:id format */
      {"user_id":"user:123456789021"}
    ]
  }
}
{% endhighlight %}

Example request to remove chat participant:

{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},             /* Chat ID in a chat:id format */
  "chat_control":{
    "remove_member":{"user_id":"user:123456789012"}         /* User ID in a user:id format */
  }
}
{% endhighlight %}

Example request to leave chat by user:

{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},             /* Chat ID in a chat:id format */
  "chat_control":{
    "leave":"true"                                          
  }
}
{% endhighlight %}

**New message creation**

This is a key feature of this method.

To create a new message you need to send a POST-payload data with a message object which is similar to an object that you 
can get with me/messages/get method.

Text message example:

{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},         /* Chat ID in a chat:id format */
  "message":{                                           /* Message content */
    "text":"Hello"                                      /* Message text */
  }
}
{% endhighlight %}

A message with an IMAGE attachment can be sent:

{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},                     /* Chat ID in a chat:id format */
  "message":{                                                       /* Message content */
    "attachment":{
      "type":"IMAGE",
      "payload":{"url":"https://st.mycdn.me/res/i/ok_logo.png"}     /* Resource URL */
    }
  }
}
{% endhighlight %}

Support for other attachment types (VIDEO, SHARE, AUDIO) will be added in future.

**Current user state**

Current user can inform other chat participant about some of his actions or his state:

* mark all messages as seen - mark_seen;
* user us typing a new message - typing_on;
* user is sending new file (video, audio, image) - sending_photo.

Example request: 

{% highlight json %}
{
  "recipient":{"chat_id":"chat:C3ecb9d02a600"},     /* Chat or dialog id */
  "sender_action":"mark_seen"                       /* Possible values: sending_photo, sending_video, sending_audio */
}
{% endhighlight %}

**Direct user messages**

It is possible to send a message from group to a single or multiple users at once.

User must allow to receive group messages before it can be sent to him.

Following message syntax is used for this purpose:
{% highlight json %}
{
    "recipient":{
        "user_ids":[                                /* List of user ids in user:id or id format*/
            "user:123456789012",                    
            "210987654321"
        ]
    },
    "message":{                                     /* Message content */
        "text":"Hello"                              /* Message text */
    }
}
{% endhighlight %}

Each user from the list will get a message in his own group-to-user chat.

API will respond with a list of boolean results indicating if a message was sent successfully or an error has occurred during this process.

{% highlight json %}
{
  "success": [                                          
    false,
    false
  ]
}
{% endhighlight %}