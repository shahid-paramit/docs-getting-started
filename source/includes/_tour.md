# The two-minute tour

This is a simple tutorial on how to build a pipe with Flex.io. In this example we will build a pipe that will grab all of the files in a Github folder and output the to a Dropbox folder.

Here's how to do it:

##### 1. Create a new pipe by clicking the **New Pipe** button

(image)
new pipe modal

This will open the **New Pipe** modal. If you'd like, you can name the pipe here and add a description. When you're done click **Web Link** to select the type of input connection you'd like to use.

(image)
file chooser

This is the file chooser step for the pipe. You can skip this step by clicking the **Create Pipe** button, but for our example, we'll specify a couple of files from a Github repository.

We'll use some data from our friends at fivethirtyeight who provide all of the data on Github for the articles they write.

(image)
https://github.com/fivethirtyeight/data/tree/master/presidential-campaign-trail

To get the URL for the raw files, we'll do the following:

* Click on each file we want
* Click the **Raw** button
* Copy the URL from the browser window into the file chooser in Flex.io.

Once we're done adding the URLs we want for our pipe input, click the **Create Pipe** button.

Our pipe has been created. Double-click on the pipe to open the pipe builder view.

(image)
pipe builder

We can see the input tile for this pipe which has the URLs we enter. Run the pipe by click the **Run Pipe** button.

Once the pipe has been run, you'll see the two files listed in the input list and their corresponding data file in the content area

Clicking on each file in the input list will show the preview of that file in the content area.

At this point, our pipe doesn't do a whole lot, so let's add a step to change the data a bit.

Click the **+** tile to the right of the input tile to add a step.

Type `convert` into the command bar below the pipe tiles and then click the **save** button in the command bar. This will convert the files into tables.

<aside class="notice">
The <code>convert</code> command is a shorthand which converts a text-delimited file into a table using standard choices for CSV files. The verbose syntax for this command would be <code>convert from: delimited to: table delimiter: comma qualifier: double-quote header: true</code>.
</aside>

Type `transform case: upper` into the command bar and press <code>Ctrl+Enter</code>

<aside class="notice">
Pressing <code>Ctrl+Enter</code> is an easy way to save the step and update the pipe without having to click the <b>Save</b> button in the command bar.
</aside>

(image)
table with transform column highlighted

We can see the result of this step in the table in the content area. The `location` column has been converted to all capital letters.

The final step is to output these files to a folder in Dropbox.

Clikc the **Add Output** tile in the pipe list to open the output file chooser.

(image)
output file chooser

Since we're just getting started, we'll need to set up a connection to our Dropbox account. Click **Dropbox** to configure the connection. This will open the **New Connection ** modal.

Click on the **Authenticate your Dropbox account** button and enter your Dropbox username and password.

<aside class="notice">
This information is out submitted to Dropbox! Flex.io does not store your password for Dropbox, Google Drive or any other connections which use OAuth.
</aside>

Once you've entered your username and password, the window should close and your should see a message that says "You've successfully connected to Dropbox!".

Click the **Create Connection** button. The **New Connection** modal will close and the **Output File Chooser** modal will open up.

(image)
output folder chooser

Select the folded you'd like to output the files to by either double-clicking on the folders in the file list or typing the folder name in the "Output folder" text box.

Click the **Done** button.

Click the **Save** button in the command bar.

<aside class="notice">
Pipes will only output to when formally running the pipe. In order for our output get piped to Dropbox, we need to click the <b>Run Pipe</b> button.
</aside>

Click the **Run Pipe** button.

Open up Dropbox folder to see the files there.
