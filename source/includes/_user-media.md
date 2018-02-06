# User-Media

## Delete User-Media

```shell
curl "https://example.com/api/v1/user-media"
  -X DELETE -d '{"fileIds": "Skeppsholmen", "parentId": 1120039}'
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  fileIds: [646525, 646525]
}
Renderforest.deleteUserMedia(payload)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": [
    [ 1 ],
    [ 0 ]
  ] 
}
```

This endpoint deletes a specific sound.

### HTTP Request

`DELETE https://example.com/api/v1/user-media`

### Body Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
fileIds   |  ✔       | ✘       | An array of user-media Id's to delete.


## Add User-Media Folder

```shell
curl "https://example.com/api/v1/user-media/folders"
  -H "Authorization: 'mock-authorization'"
  -X POST -d '{"name": "Skeppsholmen", "parentId": 1120039}'
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  name: 'Skeppsholmen',
  parentId: 1120039
}
Renderforest.addUserMediaFolder(payload)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 201,
  "message": "Created",
  "data": {
    "id": 1495403,
    "user_id": 1469277,
    "parent_id": 1120039,
    "name": "Skeppsholmen",
    "path": "user_1469277/My_Images/Skeppsholmen",
    "status": 1,
    "updatedAt": "2018-02-06T08:37:12.715Z",
    "createdAt": "2018-02-06T08:37:12.715Z"
  }
}
```

This endpoint creates user-media folder.

### HTTP Request

`POST https://example.com/api/v1/user-media/folders`

### Body Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
name      |  ✔       |  ✘      | The name of the user-media folder.
parentId  |  ✘       |  0      | The parent Id of the user-media folder.

<aside class="success">
 If no parentId is specified, then the user-media folder is created in the root folder.
</aside>


## Get User-Media Folder

```shell
curl "https://example.com/api/v1/user-media/folders/1367155"
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  folderId: 1367155
}
Renderforest.getUserMediaFolder(payload)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": {
    "id": 1367155,
    "name": "Stockholm, Sweden",
    "parent_id": 1120039,
    "folders": [
      {
        "id": 1495402,
        "name": "Old Town",
        "parent_id": 1367155
      }
    ],
    "files": [
      {
        "id": 5985247,
        "user_id": 1469277,
        "folder_id": 1367155,
        "mime": "image/jpeg",
        "file_name": "2016-03-22 11.37.59.jpg",
        "file_path": "https://example.com/user_1469277/My_Images/new_folder/db8ad8c8-f7ab-4a99-a7b2-210abfce2d86.jpg",
        "thumbnail_path": "https://example.com/user_1469277/My_Images/new_folder/thumb_bbac2490-bc92-4d12-83d2-1140d429b5bf.jpg",
        "status": 1,
        "width": 1440,
        "height": 1920,
        "filesize": 1656684,
        "duration": 0,
        "thumb_video": null,
        "webp_path": "https://example.com/user_1469277/My_Images/new_folder/b68ee8c4-264c-4502-9b0c-2c5c2fca0609.webp",
        "frame_image": null,
        "fieldname": "70b01a00-eda7-11e7-adfa-836a81ae1d29",
        "createdAt": "2017-12-30T17:22:06.022Z",
        "updatedAt": "2017-12-30T17:22:06.022Z"
      },
      {
        "id": 5985252,
        "user_id": 1469277,
        "folder_id": 1367155,
        "mime": "image/jpeg",
        "file_name": "2016-03-22 12.58.43.jpg",
        "file_path": "https://example.com/user_1469277/My_Images/new_folder/ed5176eb-fff2-486c-994c-86faa1351ab5.jpg",
        "thumbnail_path": "https://example.com/user_1469277/My_Images/new_folder/thumb_c25aa4e4-0e6c-41c5-b422-efb1aafb1b80.jpg",
        "status": 1,
        "width": 1920,
        "height": 1440,
        "filesize": 2211797,
        "duration": 0,
        "thumb_video": null,
        "webp_path": "https://example.com/user_1469277/My_Images/new_folder/955fd8f5-1539-43dc-b659-7ae46948cfd6.webp",
        "frame_image": null,
        "fieldname": "7fcf8fc0-eda7-11e7-adfa-836a81ae1d29",
        "createdAt": "2017-12-30T17:22:33.602Z",
        "updatedAt": "2017-12-30T17:22:33.602Z"
      }
    ]
  }
}
```

This endpoint retrieves the user-media folder with entire content.

### HTTP Request

`GET https://example.com/api/v1/user-media/folders/<folderId>`

### URL Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
folderId  |  ✘       |  0      | The Id of the user-media folder to retrieve.

<aside class="success">
 The folderId of the user-media root folder is 0.
</aside>


## Update User-Media Folder (partial update)

```shell
curl "https://example.com/api/v1/user-media/folders/1495403"
  -X PATCH -d '{"name": "Skeppsholmen, Stockholm", "parentId": 1367155}'
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  folderId: 1495403,
  name: 'Skeppsholmen, Stockholm',
  parentId: 1367155
}
Renderforest.updateUserMediaFolderPartial(payload)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": {
    "id": 1495403,
    "user_id": 1469277,
    "parent_id": 1367155,
    "name": "Skeppsholmen, Stockholm",
    "path": "user_1469277/My_Images/Stockholm/Skeppsholmen",
    "status": 1,
    "updatedAt": "2018-02-06T08:37:12.715Z",
    "createdAt": "2018-02-06T10:33:06.842Z"
  }
}
```

This endpoint updates the user-media folder (partial update).

### HTTP Request

`PATCH https://example.com/api/v1/user-media/folders/<folderId>`

### URL Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
folderId  |  ✔       |  ✘      | The Id of the user-media folder to update.

### Body Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
name      |  ✘       |  ✘      | The name of the user-media folder.
parentId  |  ✘       |  ✘      | The parent Id of the user-media folder.

<aside class="warning">
 Note, you cannot move the folder into it's sub folder.
</aside>

<aside class="notice">
 Any of the properties can be updated separately, as well as all of them at the same time.
</aside>
