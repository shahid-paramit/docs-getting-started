# Building a pipe

You can build a pipe in the Web App using the Pipe Builder.  A longer walkthrough can be found in the [Web App Documentation](https://www.flex.io/docs/web-app/#building-and-running-a-pipe).

For this tutorial, we'll start with a blank pipe and then add an input and two operations.

##### Create a New Pipe

Let's start by creating a new pipe.

1.    Sign in to Flex.io and navigate to the Sample Project, as discussed above.

    &nbsp;

    ![New Pipe Button](https://s3.amazonaws.com/docs-assets/gs-build-new.png "New Pipe Button")

    &nbsp;

2.    Click on the New Pipe Button at the top right of the page and a New Pipe dialog will appear.

    &nbsp;

    ![New Pipe Dialog](https://s3.amazonaws.com/docs-assets/gs-build-new-dialog.png "New Pipe Dialog")

    &nbsp;

3.    Enter the following:
    * Name: Getting Started
    * Alias: username-getting-started
    * Description: This is a getting started pipe

    &nbsp;

4.    Click on the 'Blank Pipe' icon and then click the Create Pipe button.

    &nbsp;

    ![New Pipe Entry](https://s3.amazonaws.com/docs-assets/gs-build-new-pipe.png "New Pipe Entry")

    &nbsp;

5.    Double-click on the Pipe to open the Pipe Builder.

    &nbsp;

    ![New Pipe Builder](https://s3.amazonaws.com/docs-assets/gs-build-pipe-builder.png "New Pipe Builder")

    &nbsp;


##### Build a Pipe

Now, let's build some pipe steps.  We'll do an `input`, a `convert` and a `select` operation to demonstrate.

1.    Click the tile step 'Input'.  A dialog will appear to help you add an input.  You could use the dialog to get started, but, for now, click Cancel.  Then, in the command bar, paste in the following `input` command: 

    &nbsp;

    ```
    input file: https://raw.githubusercontent.com/flexiodata/sample-data/master/contacts-2016-11.csv => test.csv
    ```

    &nbsp;


    &nbsp;

    ![Input Command](https://s3.amazonaws.com/docs-assets/gs-build-input.png "Input Command")

    &nbsp;

2.    Click the Save button.  This will run the pipe through the Input step and provide you a preview of the text file.

    &nbsp;

    ![Input Command](https://s3.amazonaws.com/docs-assets/gs-build-input-save.png "Input Command")

    &nbsp;

3.    Click on the + button to add an operation.  Paste the following `convert` step into the Command Bar to convert the unstructured text into a table:

    &nbsp;

    ```
    convert from: delimited to: table delimiter: comma header: true
    ```

    &nbsp;

4.    Click the Save button to run the pipe through the conversion.  You will see a table in the preview.

5.    Click on the + button to add an operation.  Paste the following `select` step into the Command Bar to reduce the number of fields down to a limited set:

    &nbsp;

    ```
    select col: givenname, surname, streetaddress, city, state, zipcode
    ```

    &nbsp;

6.    Click the Save button to run the pipe through the field selection.  The table in the preview will now populate with only the selected fields.


At this point, you can keep adding steps to build up the pipe logic; you can also edit a step by changing the command and pressing the Save button.  To remove a step, click on the 'X' in the upper right of any tile.  If you add steps between other steps and click Save, the pipe will only run to that point.  Click the Run Pipe button to refresh your pipe.

Please see the [full pipe documentation](https://www.flex.io/docs/web-app/#pipes) for further details, along with all [command](https://www.flex.io/docs/web-app/#command-bar-operations) and [function](https://www.flex.io/docs/web-app/#functions-and-syntax) syntax.  