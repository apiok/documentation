widget.getWidgetContent

$description
Returns widget content

$params#wid
Widget id

$params#style
Widget style

$additional
See [mobile widgets](/dev/sdk/js-ext/widgets)

For several widgets batch request see {% replace_method widget.getWidgets %}.

Widgets returns encoded in Base64. Processing sample:

{% format_code OKSDK.Util.decodeUtf8(atob(widget) %}