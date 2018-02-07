# Templates


## Get All Templates

```shell
curl "https://example.com/api/v1/templates?categoryId=3&equalizer=false&limit=4"
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  categoryId: 3,
  equalizer: false,
  limit: 4
}
Renderforest.getTemplates(payload)
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
      "id": 912,
      "title": "Ultimate Icon Animation Pack",
      "videoUrl": "//player.vimeo.com/video/248458512",
      "thumb": "https://example.com/media/Screens_2017/4_gen_2017/Ultimate-Icon-Animation-Pack/249c8f83-3f4a-4474-ade0-490bb5ca0d5a.jpg",
      "video": true
    },
    {
      "id": 701,
      "title": "Explainer Video Toolkit",
      "videoUrl": "//player.vimeo.com/video/190349594",
      "thumb": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Screen/tumb400.jpg",
      "video": true
    },
    {
      "id": 942,
      "title": "Futuristic Cube Presentation",
      "videoUrl": "//player.vimeo.com/video/240152695",
      "thumb": "https://example.com/media/Screens_2017/4_gen_2017/Futuristic_Cube_Presentation/ac13db59-5751-4c64-bc04-810e0112502a.jpg",
      "video": false
    },
    {
      "id": 816,
      "title": "My Business Promotion",
      "videoUrl": "//player.vimeo.com/video/211478094",
      "thumb": "https://example.com/media/Screens_2017/Promotion/my-business-promotion/766f703e-0bbf-4dc6-b845-09d3a81f7eb8.jpg",
      "video": false
    }
  ] 
}
```

This endpoint retrieves all templates.

### HTTP Request

`GET https://example.com/api/v1/templates`

### Query Parameters

Parameter  | Required | Default | Description
---------- | -------- | ------- | -----------
categoryId |  ✘       | ✘       | The Id of the template category.
equalizer  |  ✘       | ✘       | Retrieves only equalizer templates or eliminates equalizer templates.
limit      |  ✘       | 10      | Restricts the number of templates to be retrieved.


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

This endpoint retrieves color-presets of the template.<br>
You can apply these color presets to your project to give it better and unique look.

### HTTP Request

`GET https://example.com/api/v1/templates/<templateId>/color-presets`

### URL Parameters

Parameter  | Required | Default | Description
---------- | -------- | ------- | -----------
templateId |  ✔       | ✘       | The Id of the template.

<aside class="notice">
 Notice <br>
 The number of color-presets is vary from tremplate to template.<br>
 Currently, this template has 15 color-presets, but we have included only 3 of them in our example.
</aside>


## Get Pluggable-Screens of the Template

```shell
curl "https://example.com/api/v1/templates/701/pluggable-screens"
  -H "Authorization: 'mock-authorization'"
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  templateId: 701
}
Renderforest.getTemplatePluggableScreens(payload)
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
      "id": 104,
      "name": "Characters",
      "order": 1,
      "screens": [
        {
          "id": 2125620,
          "screen_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Screen/191_man_Angry_2_n.jpg",
          "order": 1900,
          "duration": 5,
          "title": "Angry Office worker with arms crossed",
          "gif_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/191_man_Angry_2_1.gif",
          "composition_name": "191_man_Angry_2",
          "tags": "business, computer, chair, desk, laptop, mobile phone, occupation, office, worker, arms, boss, boy, businessman,chef, company, employer, professional",
          "extra_video_second": 0,
          "gif_thumb_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/Gif-thumb/191_man_Angry_2_n.jpg",
          "gif_big_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/Big-Gif/191_man_Angry_2_1.gif",
          "type": 1,
          "character_based_duration": true,
          "max_duration": 15,
          "icon_adjustable": 0,
          "areas": {
            "3562168": {
              "id": 3562168,
              "id_screen": 2125620,
              "type": "text",
              "height": 108,
              "width": 392,
              "value": "type your text here",
              "x_1": 656,
              "y_1": 224,
              "x_2": 1048,
              "y_2": 224,
              "x_3": 1048,
              "y_3": 332,
              "x_4": 656,
              "y_4": 332,
              "title": "char_Angry_2",
              "word_count": 40,
              "order": 0
            }
          }
        },
        {
          "id": 2125592,
          "screen_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Screen/195_man_Show_text%20.jpg",
          "order": 1940,
          "duration": 4,
          "title": "Scene with office worker showing text with index finger",
          "gif_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/195_man_Show_text.gif",
          "composition_name": "195_man_Show_text",
          "tags": "agent, boss, business, businessman, character, corporate, employee, necktie, office, pointing, presentation, professional, showing, teaching, tie, worker,",
          "extra_video_second": 0,
          "gif_thumb_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/Gif-thumb/195_man_Show_text%20.jpg",
          "gif_big_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/Big-Gif/195_man_Show_text.gif",
          "type": 1,
          "character_based_duration": true,
          "max_duration": 14,
          "icon_adjustable": 0,
          "areas": {
            "3562130": {
              "id": 3562130,
              "id_screen": 2125592,
              "type": "text",
              "height": 68,
              "width": 463,
              "value": "type your text here",
              "x_1": 555,
              "y_1": 245,
              "x_2": 1018,
              "y_2": 245,
              "x_3": 1018,
              "y_3": 313,
              "x_4": 555,
              "y_4": 313,
              "title": "manshow_text",
              "word_count": 30,
              "order": 0
            }
          }
        }
      ]
    },
    {
      "id": 105,
      "name": "Image Holders",
      "order": 30,
      "screens": [
        {
          "id": 2125624,
          "screen_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Screen/192_man_Show_Photo_1_n.jpg",
          "order": 1910,
          "duration": 6,
          "title": "Scene with office worker pointing out the image /1 image holder ",
          "gif_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/192_man_Show_Photo_1_1.gif",
          "composition_name": "192_man_Show_Photo_1",
          "tags": "agent, boss, business, businessman, character, corporate, employee, necktie, office, pointing, presentation, professional, showing, teaching, tie, worker,",
          "extra_video_second": 0,
          "gif_thumb_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/Gif-thumb/192_man_Show_Photo_1_n.jpg",
          "gif_big_path": "https://example.com/media/Screens_2016/3rd_gen_2016/Explainer-Video-Toolkit-3gen/Gif/Big-Gif/192_man_Show_Photo_1_1.gif",
          "type": 1,
          "character_based_duration": false,
          "max_duration": 0,
          "icon_adjustable": 0,
          "areas": {
            "3562175": {
              "id": 3562175,
              "id_screen": 2125624,
              "type": "image",
              "height": 189,
              "width": 339,
              "value": "28.jpg",
              "x_1": 604,
              "y_1": 152,
              "x_2": 943,
              "y_2": 152,
              "x_3": 943,
              "y_3": 341,
              "x_4": 604,
              "y_4": 341,
              "title": "28.jpg",
              "word_count": 0,
              "original_height": 563,
              "original_width": 936,
              "order": 0
            },
            "3562176": {
              "id": 3562176,
              "id_screen": 2125624,
              "type": "text",
              "height": 99,
              "width": 368,
              "value": "type your text here",
              "x_1": 598,
              "y_1": 371,
              "x_2": 966,
              "y_2": 371,
              "x_3": 966,
              "y_3": 470,
              "x_4": 598,
              "y_4": 470,
              "title": "man_Show_Photo_1",
              "word_count": 10,
              "order": 0
            }
          }
        }
      ]
    }
  ] 
}
```

This endpoint retrieves pluggable-screens of the template.<br>

### HTTP Request

`GET https://example.com/api/v1/templates/<templateId>/pluggable-screens`

### URL Parameters

Parameter  | Required | Default | Description
---------- | -------- | ------- | -----------
templateId |  ✔       | ✘       | The Id of the template.

<aside class="notice">
 Notice <br>
 The number of pluggable-screens is vary from tremplate to template.<br>
 Pluggable-Screens are grouped by categories. Currently, this template has 21 groups of pluggable-screens.
 We have included only 2 of them in our example with limited number of pluggable-screens for each if them.
</aside>
