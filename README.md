# Odnoklassniki API
В репозитории находятся описания открытых REST-методов Одноклассники API, теперь у внешних разработчиков также есть возможность дополнить/поправить документацию.

Найти файл с описанием нужного метода можно по пути: docs/method/<ЯЗЫК>/<КАТЕГОРИЯ\_МЕТОДА>/<ИМЯ\_МЕТОДА>.md

Пример содержимого файла:
```
users.getCurrentUser

$description
Получение информации о текущем пользователе

$params#fields
Список запрашиваемых полей

$additional
дополнительная информация
```
В каркасе документации метода уже есть список параметров и его название, остается только сделать описание. Для форматирования текста используется [Markdown](https://ru.wikipedia.org/wiki/Markdown).

Для ссылки из одного метода на другой можно воспользоваться тегом *replace_method*. Например:
```
{% replace_method users.getCurrentUser %}
```

После редактирования документации на метод, создается pull request, и кто-нибудь из команды API Одноклассников его просматривает и сливает с основной веткой. Внутренняя (репозиторий в Одноклассниках) версия документации и внешняя (репозиторий на GitHub) синхронизируются периодически для поддержания актуальности.


# Odnoklassniki API
This repository contains descriptions for public REST-methods in Odnoklassniki API. Now external developers also have the possibility to add/improve documentation.

Find the desired file with the description of the method can be on the path: docs/method/<LANGUAGE>/<METHOD\_CATEGORY>/<METHOD\_NAME>.md

An example of the file contents:
```
users.getCurrentUser

$description
Getting information about the current user

$params#fields
List of requested fields

$additional
additional information
```
The framework of the method documentation already contains a list of parameters and its name, we can only make the description. To format the text, use the [Markdown](https://en.wikipedia.org/wiki/Markdown).

To link from one method to another, you can use the tag *replace_method*. For example:
```
{% replace_method users.getCurrentUser %}
```

After editing the documentation creates pull request and someone from Odnoklassniki API team looks it and merges with the main branch. Internal (repository in Odnoklassniki) version of the documentation and external (on the GitHub repository) synchronized periodically to maintain relevance.
0Looking
