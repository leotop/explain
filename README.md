# explain
Перевод http://www.dalibo.org/_media/understanding_explain.pdf

Правки перевода приветствуются.

###Коротко об explain:

- analyse - вытащить статистику из таблиц
- explain - проверять время работы sql запросов на этой ститистике
- buffers - кешировать explain analise (в памяти или на диске)

###Схема работы с explain/django (оптимизация простых запросов):

- Создать большую таблицу
- Создать индексы в используемой таблице согласно логике запросов, которые есть в django-коде.
- Взять sql запрос из django: queryset.query или подобный запрос
- Запустить analyse для этого запроса
- При замедлениях искать, где запрос тормозит, оптимизировать запрос руками и заменять существующий запрос на оптимизированный теперь уже row-запрос.

(проверить)

Статьи об оптимизации под нагрузку
http://habrahabr.ru/post/198982/
http://habrahabr.ru/post/203320/
