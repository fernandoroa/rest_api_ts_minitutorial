### Learning with a REST API TypeScript tutorial

#### Source:

`Build a REST API in TypeScript - ExpressJS and Prisma`:  
https://www.youtube.com/watch?v=PM58NEMJgMw&ab_channel=rithmic  
Author of video has a github link, check video's description.  
This is not a fork.

#### Requirements:

sqlite3:

- Link for Ubuntu:  
  https://www.digitalocean.com/community/tutorials/how-to-install-and-use-sqlite-on-ubuntu-20-04

#### How to run:

- create `.env` file with:  
  `DATABASE_URL="file:./dev.db"`  
  `PORT=8000`

- install dependencies  
  `npm install`

- configure db:  
  `npx prisma init --datasource-provider sqlite`  
  `npx prisma generate`  
  `npx prisma db push`  
  `npx prisma db seed`

- Run API:  
  `npm run dev`

- Examples to run with `REST Client` VSCode plugin, use a `.rest` file extension to create a file with:

```json
# AUTHORS

GET http://localhost:8000/api/authors

###
GET http://localhost:8000/api/authors/1

###
POST http://localhost:8000/api/authors
Content-Type: application/json

{
	"firstName": "123",
	"lastName": "Doe"
}

###
PUT http://localhost:8000/api/authors/4
Content-Type: application/json

{
	"firstName": "1234",
	"lastName": "Doe"
}

###
DELETE http://localhost:8000/api/authors/4



# BOOKS

###
GET http://localhost:8000/api/books

###
GET http://localhost:8000/api/books/1

###
POST http://localhost:8000/api/books
Content-Type: application/json

{
	"title": "las aventuras3",
	"isFiction": true,
	"datePublished": "2011-05-04",
	"authorId": 1
}

###
PUT http://localhost:8000/api/books/1
Content-Type: application/json

{
	"title": "Sapiens 2",
	"isFiction": false,
	"datePublished": "2011-05-04",
	"authorId": 2
}

###
DELETE http://localhost:8000/api/books/4
```
