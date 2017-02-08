---
title: API Filmix

language_tabs:
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Filmix API!

# Board orders

## Variables
### board-orders-shortstory.tpl, board-orders-fullstory.tpl

Parameter | Value | Description
--------- | ------- | -----------
{order-id} |  | ID замовлення
{order-date} |  | Дата додавання замовлення
[my-order] |  | Виводити тільки, якщо твоє замовлення або для всіх адмінів
{order-url} | | Посилання на замовлення
{order-type} | | Тип замовлення
{order-name} | | Назва замовлення
[order-originname] | | Якщо оригінальна назва замовлення є, то виводити
{order-originname} | | Оригінальна назва замовлення
[order-year] | | Якщо рік замовлення є, то виводити
{order-year} | | Рік замовлення
[order-source-url] | | Якщо посилання джерела є, то виводити
{order-source-url} | | Посилання джерела
[order-source-url] | | Якщо посилання джерела є, то виводити
{order-source-url} | | Посилання джерела
{order-source-hash-url} | | Зашифроване посилання на джерело
[order-information] | | Якщо додаткова інформація є, то виводити
{order-information} | | Додаткова інформація
{order-comments} | | К-сть коментарів
{order-author-url} | | Посилання на автора
{order-author} | | Ім'я автора

### board-orders-shortstory.tpl, board-orders-fullstory.tpl

Parameter | Value | Description
--------- | ------- | -----------
{color-rating} | red,green,'' | Колір рейтингу
{order-rating} | | К-сть рейтингу

### board-orders-list.tpl

Parameter | Value | Description
--------- | ------- | -----------
{board-orders-list} | | Цикл шортсторі замовлень

## API requests


```javascript
result = {
  field: "",
  message: {
    author: "oksi",
    comments_count: "0",
    created_at: "2017-02-08 17:31:16",
    description: "Хочу цей серіал на сайт",
    id: "8",
    name: "Дневники Вампира",
    original_name: "The Vampire Diaries",
    prod_year: "2006",
    rating_neg: "0",
    rating_pos: "0",
    source_link: "https://myshows.me/view/25119/",
    type: "Сериал",
    user_id: "17"
  }
  type: "error"
}
```

### Create order

#### HTTP Request

`POST /api/orders/create`

#### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
type | true | Можливі варіанти: фільм, серіал, саундтрек, торрент, інше.
name | true | Назва фільму чи іншого.
original_name | false | Оригінальна назва.
prod_year | false | Рік.
source_link | false | Посилання на джерело.
description | false | Додаткова інформація (макс. символів - 2000).

```javascript
result = {
  field: "",
  message: {
    author: "oksi",
    comments_count: "0",
    created_at: "2017-02-08 17:31:16",
    description: "Хочу цей серіал на сайт",
    id: "8",
    name: "Дневники Вампира",
    original_name: "The Vampire Diaries",
    prod_year: "2006",git push
    rating_neg: "0",
    rating_pos: "0",
    source_link: "https://myshows.me/view/25119/",
    type: "Сериал",
    user_id: "17"
  }
  type: "error"
}
```

### Get info order

#### HTTP Request

`POST /api/orders/info`

#### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
id | true | Id замовлення.