# DummyAPI

Здесь представлено описание тестирования проекта DummyAPI

## Оглавление
1. [Описание проекта](#описание-проекта)
    1. [POST](#post)
        1. [GET /post (get List)](#get-post-get-list)
        2. [POST /post/create (Create Post)](#post-postcreate-create-post)
2. [Майнд-карта](#майнд-карта)
3. [Коллекции Postman](#коллекции-postman)
4. [Баг-репорты](#баг-репорты)

## Описание проекта

https://dummyapi.io/  - данный сайт представляет собой сервис для тестирования API
Для выполения запросов необходим App ID, который можно получить автоматически после регистрацию на сайте. В качестве тестирования было взят объект __Post__

### POST
___
#### GET /post (get List)
Возвращает список постов отсортированный по дате создания.
- Доступны параметры запроса разбиения на страницы. 
- Доступны созданные параметры запроса. 

__Response Body__:

__List__
```Javascript
{
data: Array(Model)
total: number(total items in DB)
page: number(current page)
limit: number(number of items on page)
}
```
__Post Preview__
```Javascript
{
id: string(autogenerated)
text: string(length: 6-50, preview only)
image: string(url)
likes: number(init value: 0)
tags: array(string)
publishDate: string(autogenerated)
owner: object(User Preview)
}
```
__User Preview__
```Javascript
{
id: string(autogenerated)
title: string("mr", "ms", "mrs", "miss", "dr", "")
firstName: string(length: 2-50)
lastName: string(length: 2-50)
picture: string(url)
}
```
___
#### POST /post/create (Create Post)
Создает новый пост. Возвращает данные о посте

__Request body__:

```javascript
{
text: string(length: 6-50, preview only)
image: string(url)
likes: number(init value: 0)
tags: array(string)
owner: string(User id)
}
```
__Response body__:

__Post__
```javascript
{
id: string(autogenerated)
text: string(length: 6-1000)
image: string(url)
likes: number(init value: 0)
link: string(url, length: 6-200)
tags: array(string)
publishDate: string(autogenerated)
owner: object(User Preview)
}
```
__User Preview__
```Javascript
{
id: string(autogenerated)
title: string("mr", "ms", "mrs", "miss", "dr", "")
firstName: string(length: 2-50)
lastName: string(length: 2-50)
picture: string(url)
}
```
## Майнд-карта
Данная МК представляет собой наор тестов для тестирования объекта __Post__. Подробная проверка расписана для __Get Post__ и __Create Post__
![Alt-текст](https://i.imgur.com/rOKy4iP.png"МК")

Также майнд-карту можно [скачать](https://github.com/SergeyQC/DummyAPI/blob/main/DummyAPI.xmind)

## Коллекции Postman

Для удобства и увелечения скорости тестирования, создано окружение с заранее сохраненным host, его можно [скачать](https://github.com/SergeyQC/DummyAPI/blob/main/DummyAPI_postman_environment.json)

Запросы были объеденыне в одну коллекцию и разбиты на две папка, для удобства ее экспортирования любым членом команды, ее можно [скачать](https://github.com/SergeyQC/DummyAPI/blob/main/Post.postman_collection.json)

## Баг-репорты

В процессе тестировнаия были найдены не соотвествия с ожидаемым результатом и заведены баг-репорты

В качестве примера, прикрепил скрин одного из них:
![Alt-текст](https://i.imgur.com/KrR4you.png"МК")

Более подробно с ними можно ознакомиться по [ссылке](https://docs.google.com/spreadsheets/d/1XoW6kW8iGQ1St1mtUD3-C-Yx2XklgPDXD6QuUGC3bW4/edit?usp=sharing)
