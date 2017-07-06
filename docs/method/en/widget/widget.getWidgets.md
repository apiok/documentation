widget.getWidgets

$description
Retrieves UI widgets to build into your app

$params#wids
Widget ids

$params#style
Widget style (applied for all requested widgets. if any of them does not support the style, it will be loaded with a default one)

$additional
See [mobile widgets](/dev/sdk/js-ext/widgets)

Content returns encoded in Base64. Processing sample:

{% format_code OKSDK.Util.decodeUtf8(atob(data[i].content) %}