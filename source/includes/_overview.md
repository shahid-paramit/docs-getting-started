# Overview

## Getting Started

> To return basic status information about the current user, enter the following:

```shell
curl -X GET 'https://www.flex.io/api/v1/status'
-H "Authorization: Bearer [[app:Authorization]]"
-H "Content-Type: application/json; charset=utf-8"
```

> The above command returns JSON structured like this:

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

## Authentication

All API calls use the following root: https://www.flex.io/api/v1/

Most API calls must be authenticated. API calls are authenticated by passing the API key in the Authorization HTTP header:

Authorization: Bearer [[app:Authorization]]
