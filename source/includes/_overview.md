# Overview

## Getting Started 2

### Test Heading 3

```shell
curl -X GET 'https://www.flex.io/api/v1/status'
-H "Authorization: Bearer [[app:Authorization]]"
-H "Content-Type: application/json; charset=utf-8"
```

```json
{
  "user_loggedin": true,
  "user_name": "john",
  "user_eid": "ktzsnpqgvwjm"
}
```

The Flex.io API allows users to run pipe, configure and manage the running pipe process, and read the resulting pipe process output.  Users can set inputs and read outputs so that files can be easily processed with the pipe logic at runtime.

To begin using the API, do the following:

1. Create an account
2. Get your API key
   - go to the account area
   - click on the API tab
   - click on "Create API Key"
3. Create your first API request:
   - create an HTTP GET Request for "/api/v1/status"
   - set the Authorization header to your API key: "Authorization: Bearer [[app:Authorization]]"
   - set the content type to JSON: "Content-Type: application/json; charset=utf-8"

<aside class="notice">
You can use either a <code>*</code> or a <code>-</code> to create bulleted lists.
</aside>

<aside class="warning">
You can also tell the user that this is something bad to do...
</aside>

<aside class="success">
...or that this is something good to do. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi id erat bibendum, rutrum justo ac, venenatis metus. Morbi lobortis lacinia tellus, ut gravida mi elementum sed. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.
</aside>

## Authentication

All API calls use the following root: https://www.flex.io/api/v1/

Most API calls must be authenticated. API calls are authenticated by passing the API key in the Authorization HTTP header:

Authorization: Bearer [[app:Authorization]]
