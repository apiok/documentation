market.setStatus

$description
Set product status

$params#product_id
Product ID

$params#product_status
Product status

$additional
There are two different status flows for groups and public pages.

**Flow for groups**

|Current status		|Possible new status|
|-----------|-------|
|ACTIVE	|SOLD, CLOSED		|
|CLOSED		|ACTIVE |
|AUTO_CLOSED		|ACTIVE		|
|SOLD		|ACTIVE		|

**Flow for public pages**

|Current status		|Possible new status|
|-----------|-------|
|ACTIVE	|OUT_OF_STOCK, CLOSED	|
|CLOSED		|ACTIVE |
|AUTO_CLOSED		|ACTIVE		|
|OUT_OF_STOCK		|ACTIVE		|