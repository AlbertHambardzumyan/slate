---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

includes:
  - errors

search: true
---

# Introduction

Welcome to the Renderforest API! You can use our API to:

 - Upload Media (Image, Video, Sound)
 - Manipulate Project-Data
 - Fetch Templates
 - Fetch & Remove Sounds
 - Fetch Current User

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: 'mock-authorization'"
```

> Make sure to replace `mock-authorization` with one you have to generate.

Renderforest uses authorization string to allow access to the API.

Renderforest expects for the authorization string to be included in all API requests to the server in a header that looks like the following:

`Authorization: 'mock-authorization'`

<aside class="notice">
You must replace <code>'mock-authorization'</code> with one you have to generate.
</aside>

# Sounds

## Get All Sounds

```shell
curl "https://example.com/api/v1/sounds?duration=4"
  -H "Authorization: 'mock-authorization'"
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

<aside class="success">
Remember — any greater value of the duration than 180 will be overriden by 180!
</aside>

## Delete a Specific Sound

```shell
curl "https://example.com/api/v1/sounds/2"
  -X DELETE
  -H "Authorization: 'mock-authorization'"
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": "TBD" 
}
```

This endpoint deletes a specific sound.

### HTTP Request

`DELETE https://example.com/api/v1/sounds/<ID>`

### URL Parameters

Parameter | Required | Description
--------- | -------- |-----------
ID        |  ✔       | The ID of the sound to delete.

