# Using the API

The Flex.io API allows users to run pipes, configure and manage the pipe process as well as read the pipe process output.  Users can set inputs and read outputs so that files can be easily processed with the pipe logic at runtime.

The Flex.io API is organized around REST: pipes, processes, and other resources are accessed with URL endpoints and manipulated using GET, POST, and DELETE HTTP verbs.  Results are returned as JSON.  Errors are returned using HTTP error codes.

##### Accessing an API Key

To use the API, you'll need an API key:

1. Sign into Flex.io
2. Once you've signed into Flex.io, click on your user profile in the upper-right and click on 'Account' from the dropdown menu.
3. In the Account area, select the 'API' tab.
4. In the API area, click on the Create API Key button to generate a new API key

 ![API Key](https://s3.amazonaws.com/docs-assets/gs-api-key.png "API Key")

##### Examples

Once you have an API key, you can list your pipes by doing the following:

1. create an HTTP GET request on "https://www.flex.io/api/v1/pipes"
2. set the Authorization header to your API key: "Authorization: Bearer :token"

For example, in CURL, this would look like

```
curl -X GET 'https://www.flex.io/api/v1/pipes'
-H "Authorization: Bearer zxcvzxcvzxcvzxcv"
```

You can also run your pipes by doing the following:

1. create an HTTP POST request on "https://www.flex.io/api/v1/pipes/chicago-homicides-v1/run"
2. set the Authorization header to your API key: "Authorization: Bearer :token"

```
curl -X GET 'https://www.flex.io/api/v1/pipes/chicago-homicides-v1/run'
-H "Authorization: Bearer zxcvzxcvzxcvzxcv"
```

Further details on the API can be found in the [API Reference Documentation](https://www.flex.io/docs/api/).