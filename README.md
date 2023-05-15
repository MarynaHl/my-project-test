## Description

The task is to create a simple REST application from scratch. To reduce implementation time, please use the NestJS framework (this is a MUST, don’t use any other framework). The application should implement a nodeJS server API communicating with this: https://reqres.in/

Use prerequisites below:
- use TypeScript 3.4 and above. 
- use NestJS Framework, https://docs.nestjs.com/ 
- use MongoDB 4.4 and above 
- use RabbitMQ 3.7 and above

The REST app should consist of:

- POST /api/users
On the request store the user entry in db. After the creation, send an email and rabbit event. Both can be dummy sending (no consumer needed).

- GET /api/user/{userId}
Retrieves data from https://reqres.in/api/users/{userId} and returns a user in JSON representation.

- GET /api/user/{userId}/avatar
Retrieves image by 'avatar' URL.
On the first request it should save the image as a plain file, stored as a mongodb entry with userId and hash. Return its base64-encoded representation.
On following requests should return the previously saved file in base64-encoded. representation (retrieve from db).

- DELETE /api/user/{userId}/avatar
Removes the file from the FileSystem storage.
Removes the stored entry from db.

### Delivery

Your project passes eslint
The project builds and can start
All endpoints can be requested from postman
Data is stored in database successfully and rabbit event is emitted
Your application is covered with unit/functional tests

## Installation

```bash
$ npm install
$ docker compose up
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## License

Nest is [MIT licensed](LICENSE).
