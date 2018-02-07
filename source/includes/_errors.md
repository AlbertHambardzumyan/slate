# Errors

<aside class="notice">
 Notice <br>
 The Renderforest API uses the following error codes:
</aside>


Status      | Code                | Message
----------- | ------------------- | -----------------------------------------------------
400         | BadRequest          | ✍
401         | Unauthorized        | Authorization required.
403         | Forbidden           | The user is blocked.
404         | NotFound            | Media folder with id: {id} is not found.
            |                     | The specified resource path does not exist.
            |                     | The sound with id: {id} is not found.
            |                     | The tariff plan resource is not found.
            |                     | The template with id: {templateId} is not found.
            |                     | The user resource is not found.
409         | Conflict            | You cannot move the folder into it's sub folder.
409         | Conflict            | ✍
422         | UnprocessableEntity | ✍
500         | InternalError       | The server encountered an internal error. Try again later.


<aside class="warning">
 Warning <br>
 The message property of the errors are vary. We have listed few of them to give you an overview of it.
 We reserve the right to change our API error's message at any time, thus we encourage you to stick to the error's
  status and code properties.
</aside>
