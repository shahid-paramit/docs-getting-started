# Using the command line

The Flex.io Command Line Interface (CLI) is a tool for managing and running your Flex.io services from the command line. With just one compact utility, you can integrate Flex.io services into your scripts and command-line environment, enabling direct integration with other systems and software.

Once you've installed and configured the CLI, you'll be able to see a list of your pipes and run them from the client.  You can even feed data from the command line into the pipe for processing, then get back the results.

##### Install the CLI

Several different versions of the command line are available; [see here for a complete list of options](https://github.com/flexiodata/flexio-cli-js).  For demonstration purposes here, we'll use the js client, which you can easily install with npm:

1. Make sure you've downloaded and installed [Node.js](https://nodejs.org/en/)
2. At the command prompt, enter the following command:

    &nbsp;

    ```
    $ npm install -g flexio
    ```


##### Configure the CLI

After installation, you'll next need to configure the CLI with an API key.  Create an API Key as follows:

1. Sign into Flex.io
2. Once you've signed into Flex.io, click on your user profile in the upper-right and click on 'Account' from the dropdown menu.
3. In the Account area, select the 'API' tab.
4. In the API area, click on the Create API Key button to generate a new API key

    &nbsp;

    ![API Key](https://s3.amazonaws.com/docs-assets/gs-api-key.png "API Key")

5. Once you've generated the API key, go back to the command line and enter the following:

    &nbsp;

    ```
    $ flexio configure
    ```

    &nbsp;

6. Next you'll be prompted to enter your API key:

    &nbsp;

    ```
    $ flexio configure
    Configuring profile 'default'
    Please enter your API key: <paste your api key here>
    ```

    &nbsp;

##### Listing and Running your Pipes

Now that you've installed and configured the command line, you're ready to list and run your pipes:

1. To list your pipes, enter the following at the command prompt:

    &nbsp;

    ```
    $ flexio pipes list
    ```

    &nbsp;

2. Once you've listed the pipes, browse the list.  You'll see the identifiers (eids) for your pipes along with their aliases and descriptions.  For example, in your list of pipes, you should see the two sample pipes from your 'Sample Project' repository with the descriptions "Review commits across multiple..." and "Select a subset of a list of contacts".  You should also see the pipe we built in the "Building a pipe" section with "Getting Started" name, alias, and description.

    &nbsp;

3. In general, to run a pipe, enter a command like 'flexio pipes run &lt;pipe-alias&gt;' at the command prompt, where &lt;pipe-alias&gt; is the alias for the pipe, which can be set when creating or editing a pipe.

    &nbsp;

    ```
    $ flexio pipes run <pipe-alias>
    ```

    &nbsp;

4. Let's run the 'Getting Started' sample pipe, assuming the alias is 'paul-getting-started':

    &nbsp;

    ```
    $ flexio pipes run paul-getting-started
    ```

    &nbsp;

5. If we want to get back the data from the output, we add the "--output data" parameter to the command:

    &nbsp;

    ```
    $ flexio pipes run <pipe-alias> --output data
    ```

    &nbsp;

6. Let's get back the output for the 'Getting Started' sample pipe, assuming the alias is 'paul-getting-started':

    &nbsp;

    ```
    $ flexio pipes run paul-getting-started --output data
    -or-
    $ flexio pipes run paul-getting-started --output data > output.txt
    ```

    &nbsp;


7. With the command line, it's also possible to send input files or stdin to a pipe.

    &nbsp;

    ```
    $ flexio pipes run <pipe-alias> file.txt
    -or-
    $ flexio pipes run <pipe-alias> file.txt *.csv
    -or-
    $ echo Hello, World | flexio pipes run <pipe-alias>
    ```

    &nbsp;


Further details on the CLI and SDKs can be found in the [API Reference Documentation](https://www.flex.io/docs/api/).

