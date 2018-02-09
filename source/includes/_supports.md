# Supports

## Add Supports Ticket

```shell
curl "https://example.com/api/v1/supports/ticket"
  -H "Authorization: 'mock-authorization'"
  -X POST -d '{"message": "I need to...", "mailType": "Sales", "subject": "Some help in .."}'
```

```javascript
const Renderforest = require('@renderforest/sdk-js')

const payload = {
  message: 'I need to...',
  mailType: 'Sales',
  subject: 'Some help in ..'
}
Renderforest.addSupportsTicket(payload)
  .then(console.log) // handler the success
  .catch(console.error) // handler the error
```

> The above command returns JSON structured like this:

```json
{
  "status": 200,
  "message": "OK",
  "data": {
    "ticketId": 12614,
    "messageId": "<ef06ec88-38a9-237c-7f71-24555bb800de@renderforest.com>"
  } 
}
```

This endpoint creates supports ticket.

### HTTP Request

`POST https://example.com/api/v1/supports/ticket`

### URL Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
message   |  ✔       | ✘       | The message of the ticket.
mailType  |  ✔       | ✘       | The type of the ticket.
subject   |  ✘       | ✘       | The subject of the ticket.

<aside class="warning">
 Warning <br>
 The possible values of ticket mailType are: 'Sales', 'Report a bug', 'Editing process', 'Creative team', 'Other'.
</aside>
