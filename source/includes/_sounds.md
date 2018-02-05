# Sounds

## Get All Sounds

```shell
curl "https://example.com/api/v1/sounds?duration=4"
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

Renderforest.getSounds(4)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": [
    {
      "id": 646692,
      "id_user": 1469277,
      "title": "sound sample.mp3",
      "duration": 12,
      "path": "https://example.com/user_1469277/ba63c175-3bdc-4e47-a357-7fb7d08f508b.mp3",
      "low_quality": null,
      "voice_temp": null,
      "voice_over": 0,
      "filesize": 198658,
      "status": 1
    },
    {
      "id": 631791,
      "id_user": 1469277,
      "title": "sound.mp3",
      "duration": 10,
      "path": "https://example.com/user_1469277/ba63c175-3bdc-4e47-a357-7fb7d08f508b.mp3",
      "low_quality": null,
      "voice_temp": null,
      "voice_over": 0,
      "filesize": 198658,
      "status": 1
    }
  ] 
}
```

This endpoint retrieves all sounds given the duration. It matches all sounds having <= duration from the given one.

### HTTP Request

`GET https://example.com/api/v1/sounds`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
duration  | ✔        | ✘       | The result list of sounds will have greater or equal duration to this one.

<aside class="warning">
Remember — any greater value of the duration than 180 will be overriden by 180!
</aside>

<aside class="notice">
 If the 'id_user' is not specified, then the media is from Rendeforest library. This media cannot be deleted. <br>
 Otherwise, the media belongs to the specified user. This media can be deleted by the specified user. 
</aside>

## Delete a Specific Sound

```shell
curl "https://example.com/api/v1/sounds/2"
  -X DELETE
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

Renderforest.deleteSound(2)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": {
    "affectedRows": 1
  } 
}
```

This endpoint deletes a specific sound.

### HTTP Request

`DELETE https://example.com/api/v1/sounds/<ID>`

### URL Parameters

Parameter | Required | Default |Description
--------- | -------- | ------- | -----------
ID        |  ✔       | ✘       | The ID of the sound to delete.
