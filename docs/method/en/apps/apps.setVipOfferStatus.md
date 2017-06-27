apps.setVipOfferStatus

$description
Changes VIP offer state specifying if the user got the offer's in-game bonus

$params#slot
Slot number (0 .. 4)

$params#given
Has user received a bonus for a VIP offer

$additional
An app can have no more than 5 bonus slots for each user. When offers list is renewed via {% replace_method apps.setVipOffers %}
method slot values remain the same.

It is recommended to check if user is indeed VIP before giving him a bonus.

This information can be acquired by {% replace_method users.getCurrentUser %} method when "user.VIP" fields is requested in "fields" parameter. 

Also it is important to check if user has already received this bonus by {% replace_method apps.checkVipOfferStatus %} method.