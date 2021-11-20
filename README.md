# RSCHIR_Course_NewsAggregator

# Серверная часть веб-приложения "Новостной агрегатор"


### Над курсовым проектом работал студент группы ИКБО-20-19: Эртек Хусейн Ибрахимович.

### Описание:

***Исходные данные:***

• Индивидуальное задание на разработку

Программа на вход принимает: адрес новостного сайта или его RSS-ленты и правило парсинга..

База данных агрегатора начинает автоматически пополняться новостями с этого сайта.

У пользователя есть возможность просматривать список новостей из базы и искать их по подстроке в заголовке новости.

Так же есть возможность удалить уже существующий сайт и скачать добавленые правила парсинга.

### Правила парсинга

Правила заполняются в файле формате **YAML**. Поля представляют собой название тега и css класс, по которым будет вестить поиск в html странице новостого ресурса.
 
- source: HTML или RSS (Поле, определяющее, каким будет источник новостей.
 В случае **RSS** остальные поля заполнять не обязательно, так как формат стандартный)
- feedTag: ...
- feedClass: ...
- titleTag: ...
- titleClass: ... **Обязательное поле**
- itemTag: ...
- itemClass: ... **Обязательное поле**
- descriptionTag: ...
- descriptionClass: ...
- publishedDateTag: ...
- publishedDateClass: ...
- categoryClass: ...
- categoryTag: ...
- imgClass: ...
- uriClass: ...
- uriTag: ...
- authorClass: ...

##### Примеры

В корне проекта находятся *.yml файлы с примерами:

- (https://news.yandex.ru/) - *exampleRulesHTMLYandex.yml*

- (https://news.mail.ru/politics/) - *exampleRulesHTMLMailRU.yml*

- (https://lenta.ru/rss/) - *exampleRulesRSS.yml* (Или любая другая RSS-лента: https://snob.ru/rss/all, ...)


### Сборка и запуск

 1. Запуск через IDE:
    1. В конфигурации запуска выбирать Spring Boot, также необходимо указать MainClass 
    2. Нажать *Run* и приложение запустится на embedded tomcat. Порт по умолчанию 8080.
    3. В адресную строку ввести "*localhost:8080*" (либо кастомный порт)
 2. Запуска через терминал:
    1. Запустить команду `gradlew clean build` в терминале в корне проекта. После сборки в папке build/libs будет находиться *.war файл.
    2. Запустить команду `java -jar (имя вар файла).war`. Приложение запустится на embedded tomcat. Порт по умолчанию 8080.
    3. В адресную строку ввести "*localhost:8080*" (либо кастомный порт)
    
P.S в связи с тем, что на новостных ресурсах формат времени может различаться, в интерфейсе возможно различие формата даты публикации.
