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

Now, let's add some pipe steps.  We'll add `input`, `convert`, `merge`, `select`, `rename`, and `sort` steps to demonstrate.  Normally, you can set up your input and output in the overview tab.  However, for this example, we'll take a command-driven approach for all steps in the pipe.

1.    On to top-navigation bar, click the Pipe Builder tab and you will be taken to the pipe step view.  Click the "Add a Step" button and an untitled step will appear, ready for your command. Then, in the command bar, paste in the following `input` command:

    &nbsp;

    ```
    input file: https://api.github.com/repos/flexiodata/docs-web-app/commits => docs-web-app-commits, https://api.github.com/repos/flexiodata/docs-getting-started/commits => docs-getting-started-commits, https://api.github.com/repos/flexiodata/docs-api/commits => docs-api-commits
    ```

    &nbsp;


    &nbsp;

    ![Input Command](https://s3.amazonaws.com/docs-assets/gs-build-input2.png "Input Command")

    &nbsp;

2.    Click the Save Changes button.  This will save your step, but not run your pipe.

    &nbsp;

    ![Input Command](https://s3.amazonaws.com/docs-assets/gs-build-input-save2.png "Input Command")

    &nbsp;

3.    Click the Run button at the top right.  This will run the input command and provide you a preview of the api json.  As you build the pipe, you can choose when to refresh your previews by re-running.

    &nbsp;

    ![Input Command](https://s3.amazonaws.com/docs-assets/gs-build-input-run2.png "Input Command")

    &nbsp;


4.    Click on the + button at the left to add another step.  Paste the following `convert` command into the Command Bar to convert the unstructured text into a table and click Save Changes:

    &nbsp;

    ```
    convert to: table
    ```

    &nbsp;

5.    If you choose to click the Run button, you will see a table in the preview.

6.    Click on the + button to add another step.  Paste the following `merge` command into the Command Bar to combine the separate tables from the previous step into one table and click Save Changes:

    &nbsp;

    ```
    merge
    ```

    &nbsp;

7.    If you choose to click the Run button, you will see a combined table in the preview.

8.    Click on the + button to add another step.  Paste the following `select` command into the Command Bar to reduce the number of fields down to a limited set and select Save Changes:

    &nbsp;

    ```
    select col: commit.author.date, commit.author.name, commit.author.email, commit.committer.name, commit.committer.email, commit.message
    ```

    &nbsp;

9.    If you choose to click the Run button, you will see a preview populated with only the selected fields.

10.    Click on the + button to add another step.  Paste the following `rename` command into the Command Bar to rename the columns and select Save Changes:

    &nbsp;

    ```
    rename col: commit.author.date=>author_date, commit.author.name=>author_name, commit.author.email=>author_email, commit.committer.name=>committer_name, commit.committer.email=>committer_email, commit.message=>commit_message
    ```

    &nbsp;

11.    If you choose to click the Run button, you will see a preview populated with the renamed fields.

12.    Click on the + button to add another step.  Paste the following `sort` command into the Command Bar to sort the table and click Save Changes:

    &nbsp;

    ```
    sort col: author_date desc
    ```

    &nbsp;

13.    Click the Run button to refresh your pipe.  The table in the preview will now populate with the sorted results.

At this point, you can keep adding steps to build up the pipe logic; you can also edit a step by changing the command and pressing the Save Changes button.  To remove a step, hover over the tile next to the step and an 'X' will appear, then click to delete.   Inputs and outputs may also be added directly in the pipe overview tab.

Please see the [full pipe documentation](https://www.flex.io/docs/web-app/#pipes) for further details, along with all [command](https://www.flex.io/docs/web-app/#command-bar-operations) and [function](https://www.flex.io/docs/web-app/#functions-and-syntax) syntax.
