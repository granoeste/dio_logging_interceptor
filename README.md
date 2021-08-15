# dio_logging_interceptor

An [Dio](https://pub.dev/packages/dio) interceptor which logs HTTP request and response data.

## Usage:

```dart
  final dio = Dio();

  dio.interceptors.add(
    DioLoggingInterceptor(
      level: Level.body,
      compact: false,
    ),
  );
```

## Sample output:

```
[DIO]--> POST http://localhost:9002/graphql
[DIO][HEADER]accept:*/*
[DIO][HEADER]content-type:application/json; charset=utf-8
[DIO][DATA]{
[DIO][DATA]  "operationName": "viewer",
[DIO][DATA]  "variables": {},
[DIO][DATA]  "query": "query viewer {\n  __typename\n  viewer {\n    __typename\n    id\n    username\n    firstName\n    lastName\n    email\n    password\n    phone\n    userStatus\n  }\n}"
[DIO][DATA]}
[DIO]--> END POST
[DIO]<-- 200 OK
[DIO][HEADER]connection:[keep-alive]
[DIO][HEADER]x-powered-by:[Express]
[DIO][HEADER]access-control-allow-credentials:[true]
[DIO][HEADER]keep-alive:[timeout=5]
[DIO][HEADER]date:[Sun, 15 Aug 2021 15:47:00 GMT]
[DIO][HEADER]vary:[Origin]
[DIO][HEADER]content-length:[249]
[DIO][HEADER]etag:[W/"f9-SBi3WV2NHnvyW3BEZe3/QHq1y3k"]
[DIO][HEADER]content-type:[application/json; charset=utf-8]
[DIO][DATA]{
[DIO][DATA]  "data": {
[DIO][DATA]    "__typename": "Query",
[DIO][DATA]    "viewer": {
[DIO][DATA]      "__typename": "User",
[DIO][DATA]      "id": "MTU2MjYyNjYzMQ==",
[DIO][DATA]      "username": "tan",
[DIO][DATA]      "firstName": "Georgiana",
[DIO][DATA]      "lastName": "Bosco",
[DIO][DATA]      "email": "Jamarcus4@hotmail.com",
[DIO][DATA]      "password": "7LpKbUQQeiQya8W",
[DIO][DATA]      "phone": "289.733.0250",
[DIO][DATA]      "userStatus": 10009
[DIO][DATA]    }
[DIO][DATA]  }
[DIO][DATA]}
[DIO]<-- END HTTP
```
