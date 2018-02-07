# Templates


## Get a Specific Template

```shell
curl "https://example.com/api/v1/templates/701"
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  templateId: 701
}
Renderforest.getTemplate(payload)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": {
    "id": 701,
    "title": "Explainer Video Toolkit",
    "description": "Get rid of the boring content and inspiration killers. Amaze your audience and create a fascinating video with the help of our super functional Explainer Video Toolkit. More than 400 interactive scenes, including characters, various items, kinetic typography, video and photo holders and more. It's the largest directory of astonishing animations from various fields, breathtaking music library and up to 30 minutes successful project initiative.",
    "categories": [
      {
        "title": "Other Promotional Videos",
        "id": 18,
        "parent_id": 3
      },
      {
        "title": "Christmas",
        "id": 15,
        "parent_id": 3
      },
      {
        "title": "Product or Service Promotion",
        "id": 9,
        "parent_id": 3
      },
      {
        "title": "Company Presentation",
        "id": 10,
        "parent_id": 3
      },
      {
        "title": "Infographics",
        "id": 11,
        "parent_id": 3
      },
      {
        "title": "Promotional",
        "id": 3,
        "parent_id": 1
      },
      {
        "title": "Colorful Typography",
        "id": 38,
        "parent_id": 5
      },
      {
        "title": "Clean Typography",
        "id": 36,
        "parent_id": 5
      },
      {
        "title": "Featured",
        "id": 6,
        "parent_id": 1
      },
      {
        "title": "Typography",
        "id": 5,
        "parent_id": 1
      }
    ],
    "videoUrl": "//player.vimeo.com/video/190349594",
    "rendCount": 96940,
    "durations": [
      {
        "duration": 0
      }
    ],
    "thumb": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Screen/tumb400.jpg",
    "video": true
  } 
}
```

This endpoint retrieves a specific template.

### HTTP Request

`GET https://example.com/api/v1/templates/<templateId>`

### URL Parameters

Parameter  | Required | Default | Description
---------- | -------- | ------- | -----------
templateId |  ✔       | ✘       | The Id of the template to retrieve.
