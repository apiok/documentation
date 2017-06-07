search.tagContents

$description
Get mediatopics, photos and videos by hashtags

$params#query
Tags without #

$params#filter
Where and when to count:

* since - date filter (yyyy-MM-dd HH:mm:ss)
* until - date filter (yyyy-MM-dd HH:mm:ss)
* types - content types to look into: USER_TOPIC, USER_PHOTO, USER_VIDEO, GROUP_TOPIC, GROUP_PHOTO, GROUP_VIDEO

$params#anchor
Paging anchor. Empty for first query.

$params#count
Number of results. Maximum 100.

$params#fields
Fields you want to get. Please for production usage request only fields you really need. This will number of calls you can make!

$additional
