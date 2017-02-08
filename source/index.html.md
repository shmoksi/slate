---
title: API Filmix

language_tabs:
  - shell
  - ruby
  - python
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

### Get info order

#### HTTP Request

`POST /api/orders/info`

#### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
id | true | Id замовлення.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

