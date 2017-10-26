discussions.getList

$description
Getting a list of discussions

$params#types
Types of discussions separated by a comma

$params#version
Shortcut for a set of supported types of discussions.  
For example, android.1 or ios.1 will accumulate in accordance with the PMS settings in the DiscussionType list.  
It is necessary to show "Hide all" only in case there are unread discussions that can be displayed on this device.

$params#category
The category of the discussions on which results are filtered

$params#anchor
“Anchor” for the next page with data

$params#direction
Direction for the next page with data

$params#count
The number of returned elements

$params#fields
List of requested fields separated by commas.  
If not specified the method returns default fields set.

$params#fieldset
Preset list of fields to be requested.  
All sets are stored and configured on OK’s side and are used mostly by native OK’s applications.

$params#locale
Result locale

$params#features
Features that the client supports

$additional
To work correctly in all of the following methods used by the application, the value of the version parameter must match:
{% replace_method events.get %}, {% replace_method discussions.getList %}, {% replace_method discussions.markAsRead %}, {% replace_method discussions.getDiscussionsNews %}.