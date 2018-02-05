# Users

## Get Current User

```shell
curl "https://example.com/api/v1/users/current"
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

Renderforest.getCurrentUser()
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": {
    "email": "example@gmail.com",
    "active": true,
    "last_login": "2018-02-02T09:48:31.000Z",
    "blocked": false,
    "roles": "member",
    "first_name": "example name",
    "status": 1,
    "language": "en",
    "id": 1469277,
    "rend_limit": 50,
    "upload_max_filesize": 500,
    "post_max_size": 500,
    "upload_host": "example.renderforest.com",
    "minute_limit": 60
  } 
}
```

This endpoint retrieves the current user.

### HTTP Request

`GET https://example.com/api/v1/users/current`
