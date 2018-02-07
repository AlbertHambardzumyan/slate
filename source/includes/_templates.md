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


## Get Color-Presets of the Template

```shell
curl "https://example.com/api/v1/templates/701/color-presets"
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  templateId: 701
}
Renderforest.getTemplateColorPresets(payload)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": [
    [
      "#e8fbff",
      "#ffffff",
      "#34495e",
      "#a2c4d0",
      "#eaa035",
      "#14a98b",
      "#cb4624",
      "#f6ad44",
      "#2d85ab",
      "#ac2f51"
    ],
    [
      "#7dcf81",
      "#d85252",
      "#000000",
      "#fff77c",
      "#ffffff",
      "#b67ea8",
      "#424acf",
      "#affff8",
      "#096c0f",
      "#ffaa64"
    ],
    [
      "#bfb9ff",
      "#fffa88",
      "#0b2b35",
      "#4a134d",
      "#e7e7b9",
      "#ffe5ef",
      "#a73e3e",
      "#ffffff",
      "#4b2663",
      "#75c4a7"
    ]
  ] 
}
```

This endpoint retrieves color-presets of the template.

### HTTP Request

`GET https://example.com/api/v1/templates/<templateId>/color-presets`

### URL Parameters

Parameter  | Required | Default | Description
---------- | -------- | ------- | -----------
templateId |  ✔       | ✘       | The Id of the template.

<aside class="notice">
 Note, the number of color-presets is vary from tremplate to template.<br>
 Currently, this template has 15 color-presets, but we have included only 3 of them in our example.
</aside>
