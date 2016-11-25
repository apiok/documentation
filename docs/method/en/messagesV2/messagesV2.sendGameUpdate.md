messagesV2.sendGameUpdate

$description
Send game state update message. For example user1 beats user2 high score.

$params#fid
Friend id

$params#text
Description of the update

$params#state
Will be appended to custom_args

$params#timeout
Remaining time till end of the game

$additional
The application should has CHAT platform and platform param should be set to CHAT.