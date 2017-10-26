discussions.markAsRead

$description
Mark all discussions as read

$params#version
Shortcut for a set of supported types of discussions.  
For example, android.1 or ios.1 will accumulate in accordance with the PMS settings in the DiscussionType list.  
It is necessary to show "Hide all" only in case there are unread discussions that can be displayed on this device.

$additional
To work correctly in all of the following methods used by the application, the value of the version parameter must match:
{% replace_method events.get %}, {% replace_method discussions.getList %}, {% replace_method discussions.markAsRead %}, {% replace_method discussions.getDiscussionsNews %}.