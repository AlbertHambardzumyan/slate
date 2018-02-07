---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

includes:
  - sounds
  - templates
  - user-media
  - users
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
curl "https://example.com/api/v1/..."
  -H "Authorization: 'mock-authorization'"
```

> Make sure to replace `mock-authorization` with one you have to generate.

Renderforest uses authorization string to allow access to the API.

Renderforest expects for the authorization string to be included in all API requests to the server in a header that looks like the following:

`Authorization: 'mock-authorization'`

<aside class="notice">
You must replace <code>'mock-authorization'</code> with one you have to generate.
</aside>
