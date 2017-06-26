apps.setVipOffers

$description
Sets in-game offers for VIP users.

$params#names
Bonus offer names (comma-separated)
Comma-separated list of bonus offers' names<br/>
Max name length - 50 characters<br/>
Max amount of offers - 5

$additional
App can have as much as 5 VIP offers in total at a time.

Each method's invocation completely replaces all current VIP offers with new ones.

Each offer receives an id (slot id from 0 to 4). When user starts a game through an VIP offer link parameter vipoffer=N (N = offer slotid) 
is passed as a customargs parameter value.
