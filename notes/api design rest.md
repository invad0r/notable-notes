---
tags: [curl]
title: api design rest
created: '2019-07-30T06:19:49.224Z'
modified: '2022-03-16T05:48:49.475Z'
---

# api design rest

> from `RESTful API Design – OCTO Quick Reference Card`

## general concepts

## KISS

Anyone should be able to use your API without having to refer to the documentation. 
- Use standard, concrete and shared terms, not your specific business terms or acronyms. 
- Never allow application developers to do things more than one way. 
- Design your API for your clients

(Application developers), not for your data. 
- Target major uses cases first, deal with exceptions later

```sh
GET /orders
GET /users
GET /products

curl –XPOST  -H "Accept: application/json" \
  -H "Authorization: Bearer at-80003004-19a8-46a2-908e-33d4057128e7" \
  -d '{"state":"running"}' \
  https://api.fakecompany.com/v1/users/007/orders?client_id=API_KEY_003
```

### Medium grained resources

You should use medium grained, not fine nor coarse. Resources shouldn’t be nested more than two level deep e.g.

```json
GET /users/007
{ 
  "id":"007", 
  "firstname":"James",
  "name":"Bond",
  "address":{
    "street":"H.Ferry Rd.",
    "country": { "name":"London" }
  }
}
```

consider the following five subdomains
Production       `https://api.fakecompany.com`
Tests            `https://api.sandbox.fakecompany.com`
Developer portal `https://developers.fakecompany.com`
Production       `https://oauth2.fakecompany.com`
Tests            `https://oauth2.sandbox.fakecompany.com`

---

## URLs

### Nouns

You should use `nouns`, not `verbs` (vs SOAP-RPC). `GET /orders` not `/getAllOrders` 

### Plurals

use plural nouns not singular nouns to manage two different types of resources : 
- CollecTon resource : `/users `
- Instance resource : `/users/007`

You should remain consistent. `GET /users/007` not `GET /user/007`

### Consistent case

choose between `snake_case` or `camelCase` for attributes and parameters, but remain consistent 
- `GET /orders?id_user=007`       or `GET /orders?idUser=007` 
- `POST/orders {"id_user":"007"}` or `POST/orders {"idUser":"007"}`

if you have to use more than one word in URL, you should use spinal-case (some servers ignore case). `POST /specific-orders`

### Versioning

make versioning mandatory in the URL at the highest scope (major versions). You may support at most two versions at the same time
`GET /v1/orders`

### Hierarchical structure

leverage the hierarchical nature of the URL to imply structure (aggregatoon or composition)
e.g.: an order contains products. 
`GET /orders/1234/products/1`

## CRUD-like operations

Use HTTP verbs for CRUD operations `Create/Read/Update/Delete`

```sh
Verb      Collection: /orders                 Instance: /orders/{id}

GET       Read a list orders. 200 OK         Read detail of single order. 200 OK 
POST      Create a new order. 201 Created    -
PUT       -                                  Full Update : 200 OK / Create a specific order: 201 Created 
PATCH     -                                  Partial Update. 200 OK 
DELETE    -                                  Delete order. 204 OK  
```


```sh
# POST is used to Create an instance of a collection. 
# The ID isn’t provided, and the new resource location is returned in the `Location` Header. 
POST /orders {"state":"running", "id_user":"007"}  
201 Created
Location: https://api.fakecompany.com/orders/1234 

# But remember that, if the ID is specified by the client, 

# `PUT` is used for Create.
PUT /orders/1234
201 Created

#`PUT` is used for Update to perform a full replacement. 
PUT /orders/1234 {"state":"paid", "id_user":"007"}
200 Ok


#`PATCH` is commonly used for partial Update. 
PATCH /orders/1234 {"state":"paid"}
200 Ok 

#`GET` is used to Read a collection. 
GET /orders
200 Ok
[
  {"id":"1234", "state":"paid"}
  {"id":"5678", "state":"running"}
]


# GET is used to Read an instance.      
GET /orders/1234
200 Ok
{"id":"1234", "state":"paid"}
```

---

## Query strings

### Search

You may use the “Google way” to perform a global search on multiple resources. 
`GET /search?q=running+paid`

### Filters

You should use `?` to filter resources
`GET /orders?state=payed&id_user=007`
or (multiple URIs may refer to the same resource) 
`GET /users/007/orders?state=paied` 

### Pagination

You may use a range query parameter. Pagination is mandatory : a default pagination has to be defined, for example: range=0-25.
The response should contain the following headers: `Link`, `Content-Range`, `Accept-Range`.
Note that pagination may cause some unexpected behavior if many resources are added.

```sh
/orders?range=48-55
206 Partial Content
Content-Range: 48-55/971
Accept-Range: order 10
Link : <https://api.fakecompany.com/v1/orders?range=0-7>; rel="first",
<https://api.fakecompany.com/v1/orders?range=40-47>; rel="prev",
<https://api.fakecompany.com/v1/orders?range=56-64>; rel="next",
<https://api.fakecompany.com/v1/orders?range=968-975>; rel="last"
```

### Partial responses 

You should use partial responses so developers can select informaTon needed and optimize bandwidth (mobile development). 

```sh
GET /users/007?fields=firstname,name,address(street)

200 OK

{
  "id":"007", 
  "firstname":"James",
  "name":"Bond",
  "address": {
    "street":"Horsen Ferry Road"
  }
} 
```

### Sort

Use `?sort =atribute1,atributeN` to sort resources. By default resources are sorted in ascending order.
Use `?desc=atribute1,atributeN` to sort resources in descending order
`GET /restaurants?sort=rating,reviews,name;desc=rate,reviews`

```sh
# URL reserved words : first, last, count 
# Use `/first` to get the 1st element 
GET /orders/first
200 OK
{"id":"1234", "state":"paid"}


# Use `/last` to retrieve the latest resource of a collection
GET /orders/last
200 OK
{"id":"5678", "state":"running"} !

# Use `/count` to get the current size of a collection
GET /orders/count !!
200 OK !
{"2"}
```

---

## Other concepts

### Content negotiation

Content negotiation is managed only in a pure RESTful way. The client asks for the requierd content, in the Accept Header, in order of preference. Default format is JSON. Accept: application/json, text/plain not /orders.json! 

### I18N

Use ISO 8601 standard for Date/Time/Timestamp: `1978-05-10T06:06:06+00:00` or `1978-05-10`
Add support for different Languages. Accept-Language: `fr-ca, fr-fr` not `?language=fr`

### Cross-origin requests 

Use `CORS` standard to support REST API requests from browsers (js SPA…).
But if you plane to support Internet Explorer 7/8 or 9, you shall consider specifics endpoints to add a `jsonp` support. 
- All requests will be sent with a GET method! 
- Content negoTation cannot be handled with Accept Header in Jsonp. 
- Payload cannot be used to send data. !

`POST /orders` and `/orders.jsonp?method=POST&callback=foo`
`GET /orders` and `/orders.jsonp?callback=foo`
`GET /orders/1234` and `/orders/1234.jsonp?callback=foo`
`PUT /orders/1234` and `/orders/1234.jsonp?method=PUT&callback=foo`

Warning: a web crawler could easily damage your application with a method parameter. Make sure that an OAuth2 `access_token` is required, and an OAuth2 `client_id` as well. 

### HATEOAS

Your API should propose Hypermedia links in order to be completely discoverable. But keep in mind that a majority of users wont probably use those hyperlinks, and will read the API documentation and copy/paste call examples. So, each call to the API should return in the Link Header every possible state of the application from the current state, plus self. You may use `RFC5988` Link notation to implement HATEOAS:

```sh
GET /users/007
< 200 Ok
< { "id":"007", "firstname":"James",...}
< Link : <https://api.fakecompany.com/v1/users>; rel="self"; method:"GET",
<https://api.fakecompany.com/v1/addresses/42>; rel="addresses"; method:"GET",
<https://api.fakecompany.com/v1/orders/1234>; rel="orders"; method:"GET"
```

### "Non-Resources" scenarios

In a few use cases we have to consider operations or services rather than resources.
You may use a `POST` request with a verb at the end of the URI
`POST /emails/42/send`
`POST /calculator/sum [1,2,3,5,8,13,21]`
`POST /convert?from=EUR&to=USD&amount=42`

## see also

- [[curl]]
- [[acid crud]]

