apps.setAppPromoInfo

$description
Sets information about application promo action.

$params#topic_id
Game's group topic ID with full description of the action and link to the application.  
Topic must contain a link to your application at OK.ru and has to be public

$params#text
The action's short description. Allowed length: from 8 to 48 characters

$params#start_time
Action start time in yyyy.MM.dd HH:mm format  
Must always be set to start in future

$params#end_time
Action end time in yyyy.MM.dd HH:mm format

$params#image304x128


$additional
Promo period can not be longer than 3 days.