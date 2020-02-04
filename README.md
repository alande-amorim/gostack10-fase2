# GoStack 10

## Fase 2 - Dominando Node.js

### Requirements:
In order to run this app, you'll need to have such tools installed on your computer:
- Git
- Node.js v12.14
- Yarn v1.21

### Installing & Using the app:
```bash
# clone this repo
$ git clone https://github.com/alande-amorim/gostack10-fase2.git

# cd into the repo folder
$ cd gostack10-fase2

# install dependencies
$ yarn

# run the app
$ yarn dev
```

This will start a webserver on http://localhost:3000

# REST API

- [Get all users](#get-list-of-users)
- [Get a specific user](#get-a-specific-user)
- [Create a user](#create-a-user)
- [Delete a user](#delete-a-user)

## Get list of users:
### Request:

`GET /users/`

    curl --request GET --url http://localhost:3000/users

### Response:

    X-Powered-By: Express
    Content-Type: application/json; charset=utf-8
    Content-Length: 26
    ETag: W/"1a-gsBcnOh/n2iJVQzWGF3orghGSSg"
    Date: Tue, 04 Feb 2020 00:35:25 GMT
    Connection: keep-alive

    ["Alande","Paulo","Pedro"]

## Get a specific user:
### Request:

`GET /users/:index`

    curl --request GET --url http://localhost:3000/users/1

### Response:

    X-Powered-By: Express
    Content-Type: application/json; charset=utf-8
    Content-Length: 7
    ETag: W/"7-UNfBDaHbwIjCnDwcqinZ2ZyxyzY"
    Date: Tue, 04 Feb 2020 00:39:25 GMT
    Connection: keep-alive

    "Paulo"

## Create a user:
### Request:

`POST /users`

    curl --request POST \
      --url http://localhost:3000/users \
      --header 'content-type: application/json' \
      --data '{"name": "Fulano"}'

### Response:

    X-Powered-By: Express
    Content-Type: application/json; charset=utf-8
    Content-Length: 35
    ETag: W/"23-nqhSQSMJGHus2jXeEJKGQEzFVT0"
    Date: Tue, 04 Feb 2020 00:40:41 GMT
    Connection: keep-alive

    ["Alande","Paulo","Pedro","Fulano"]

## Update a user:
### Request:

`PUT /users/:index`

    curl --request PUT \
      --url http://localhost:3000/users/0 \
      --header 'content-type: application/json' \
      --data '{
      "name": "Alande Amorim"
    }'

### Response:

    X-Powered-By: Express
    Content-Type: application/json; charset=utf-8
    Content-Length: 44
    ETag: W/"2c-PtLd5c8gIlVe33psaDZb3a0V06o"
    Date: Tue, 04 Feb 2020 00:42:44 GMT
    Connection: keep-alive

    ["Alande Amorim","Paulo","Ciclano","Fulano"]


## Delete a user:
### Request:

`DELETE /users/:index`

    curl --request DELETE \
      --url http://localhost:3000/users/0

### Response:

    X-Powered-By: Express
    Content-Type: application/json; charset=utf-8
    Content-Length: 28
    ETag: W/"1c-B0mg9u3CgZTmIOLZkW9cRt8vtUs"
    Date: Tue, 04 Feb 2020 00:43:25 GMT
    Connection: keep-alive

    ["Paulo","Ciclano","Fulano"]
