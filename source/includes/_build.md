# Building a pipe

You can build a pipe in the Web App using the Pipe Builder.  A longer walkthrough can be found in the [Web App Documentation](https://www.flex.io/docs/web-app/#building-and-running-a-pipe).  Further, a [video detailing the process can be found on YouTube here](https://www.youtube.com/watch?v=enybDpEh-2U).

For this tutorial, we'll start with a blank pipe and then add an input and a few other steps.

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
    * Alias: &lt;username&gt;-getting-started (note: &lt;username&gt; is the username you created when you signed up; so if your username is "paul", you would have "paul-getting-started")
    * Description: This is a getting started pipe

    &nbsp;


4.    Click the Create Pipe button and you will be taken to the pipe builder Overview tab.  The Pipe Overview is where you can set up your input and ouput and see a summary of your pipe steps.  If you click to the Pipe Builder tab you can view, add and edit processing steps.

    &nbsp;

    ![New Pipe Builder](https://s3.amazonaws.com/docs-assets/gs-build-pipe-builder.png "New Pipe Builder")

    &nbsp;


##### Build a Pipe

Now, let's add some pipe steps.  We'll add `input`, `convert`, `merge`, `select`, `rename`, and `sort` steps to demonstrate.

1.    Click the 'Add Input' tile.  A dialog will appear to help you add an input.  You could use the dialog to get started, but, for now, click Cancel.  Then, in the command bar, paste in the following `input` command:

    &nbsp;

    ```
    input file: https://api.github.com/repos/flexiodata/docs-web-app/commits => docs-web-app-commits, https://api.github.com/repos/flexiodata/docs-getting-started/commits => docs-getting-started-commits, https://api.github.com/repos/flexiodata/docs-api/commits => docs-api-commits
    ```

    &nbsp;


    &nbsp;

    ![Input Command](https://s3.amazonaws.com/docs-assets/gs-build-input2.png "Input Command")

    &nbsp;

2.    Click the Save button.  This will run the input command and provide you a preview of the api json.

    &nbsp;

    ![Input Command](https://s3.amazonaws.com/docs-assets/gs-build-input-save2.png "Input Command")

    &nbsp;

3.    Click on the + button to add another step.  Paste the following `convert` command into the Command Bar to convert the unstructured text into a table:

    &nbsp;

    ```
    convert to: table
    ```

    &nbsp;

4.    Click the Save button to run the conversion command.  You will see a table in the preview.

5.    Click on the + button to add another step.  Paste the following `merge` command into the Command Bar to combine the separate tables from the previous step into one table:

    &nbsp;

    ```
    merge
    ```

    &nbsp;

6.    Click the Save button to run the merge command.  You will see a combined table in the preview.

7.    Click on the + button to add another step.  Paste the following `select` command into the Command Bar to reduce the number of fields down to a limited set:

    &nbsp;

    ```
    select col: commit.author.date, commit.author.name, commit.author.email, commit.committer.name, commit.committer.email, commit.message
    ```

    &nbsp;

8.    Click the Save button to run the select command.  The table in the preview will now populate with only the selected fields.

9.    Click on the + button to add another step.  Paste the following `rename` command into the Command Bar to rename the columns:

    &nbsp;

    ```
    rename col: commit.author.date=>author_date, commit.author.name=>author_name, commit.author.email=>author_email, commit.committer.name=>committer_name, commit.committer.email=>committer_email, commit.message=>commit_message
    ```

    &nbsp;

10.    Click the Save button to run the rename command.  The table in the preview will now populate with the renamed fields.

11.    Click on the + button to add another step.  Paste the following `sort` command into the Command Bar to sort the table:

    &nbsp;

    ```
    sort col: author_date desc
    ```

    &nbsp;

12.    Click the Save button to run the sort command.  The table in the preview will now populate with the sorted results.

At this point, you can keep adding steps to build up the pipe logic; you can also edit a step by changing the command and pressing the Save button.  To remove a step, click on the 'X' in the upper right of any tile.  If you add steps between other steps and click Save, the pipe will only run to that point.  Click the Run Pipe button to refresh your pipe.

Please see the [full pipe documentation](https://www.flex.io/docs/web-app/#pipes) for further details, along with all [command](https://www.flex.io/docs/web-app/#command-bar-operations) and [function](https://www.flex.io/docs/web-app/#functions-and-syntax) syntax.
