tmbd_api
===
В этом репозитории собраны скрипты, необходимые для работы с базой данных фильмов сайта [themoviedb](https://www.themoviedb.org/) через tmbd API.

Установка
---
Для установки необходимых зависимостей в репозитории существует файл requirements.txt. Установка осуществляется этой командой:

`pip install -r requirements.txt`

Помимо этого, вам потребуется API ключ для работы с базой данных themoviedb. Его можно получить, [зарегистрировавшись](https://www.themoviedb.org/signup) на сайте, и подав заявку на получение API ключа.

Описание модулей
---
**.gitignore** Содержит файлы и директории, которые появляются в результате работы скриптов, не коммитящиеся в данный репозиторий.

**LICENSE** Содержит лицензионное соглашение для использования этого API.

**find_similar.py** Открывает предварительно созданную с помощью модуля `make_own_db.py` пользовательскую базу данных. Пользователю будет необходимо указать путь к ней. Затем запрашивает название фильма и даёт пользователю в качестве рекомендации к просмотру названия похожих фильмов. Количество рекомендаций по умолчанию = 8. Для рекомендаций фильмы выбираются основываясь на принадлежности к коллекции, родном языке озвучки, бюджете фильма и жанре.

**hello_api_TMDB.py** Проверяет на валидность API ключ пользователя.

**make_own_db.py** Создаёт пользовательскую базу данных фильмов в формате json и сохраняет её на диске. По умолчанию, новая база будет содержать до 1000 фильмов, информацию о которых она будет брать из базы данных сайта [themoviedb](https://www.themoviedb.org/)

**own_db_helpers.py** Открывает для чтения пользовательскую базу данных в формате .json и достаёт из неё все имеющиеся фильмы.

**search_in_db.py** Осуществляет поиск фильмов по ключевым словам. Запрашивает путь к заранее созданной пользовательской базе данных, в которой нужно осуществить поиск. Базу данных следует создать с помощью модуля `make_own_db.py`.

**tmdb_helpers.py** Содержит функции для запроса к API, считывания информации с базы данных в формате .json по ссылке, и проверки API ключа пользователя на валидность.
