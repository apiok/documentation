sdk.getInstallSource

$description
Возвращает положительный идентификатор места клика на приложение внутри OK

$params#adv_id
Рекламный идентификатор устройства (Advertising Identifier)

$additional
В случае если метод вернул 0 пользователь не кликал на приложение в OK в течение последних 30 дней.

**ВАЖНО**: Для того, чтобы полноценно использовать OkDevice.getAdvertisingId, необходима зависимость на com.google.android.gms:play-services-ads. Если у вас ее не будет, то на выходе вы получите ANDROID_ID вместо Advertising Identifier, т.е. передадите нам неверную информацию.

Метод следует вызывать при каждом запуске приложения, кроме тех случаев, когда вы видите, что пользователь уже авторизован через какую-то соц.сеть.

Вызов из Android SDK:

{% highlight java %}
Map<String, String> params = new HashMap<>();
params.put("adv_id", OkDevice.getAdvertisingId());
String response = ok.request("sdk.getInstallSource", params, EnumSet.of(GET, UNSIGNED));
{% endhighlight %}

{% highlight objc %}
[OKSDK getInstallSource:^(id data) {} error:^(NSError *error) {}];
{% endhighlight %}