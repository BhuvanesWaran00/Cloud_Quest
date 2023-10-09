# Set Up a Cloud Development Environment
In this practice lab, you will:
- Deploy an AWS Cloud9 environment.
- Explore the AWS Cloud9 IDE.
- Debug Python code using Cloud9 IDE
- Push changes into AWS Code commit

## Steps to Setup
- Open coud9
- click Create environment.
  1. For Name, type a name that you like for your environment.
  2. For Description, type a brief description (optional).
  3. For Environment type, choose New EC2 instance.
  4. Scroll down to the New EC2 instance.     
  1. For Instance type, review the selected option.
      - This lab requires only low RAM and vCPU usage, so the t2.micro instance is sufficient.
  2. For Platform, on the dropdown menu, keep the default value of Amazon Linux 2.
  3. For Timeout, review the cost-saving default setting of 30 minutes.
  4. Scroll down to Network settings.
  1. For Connection, choose Secure Shell (SSH).
  2. Click Create.
- In the success alert, review the message.
    - The environment might take several minutes to provision.


- In the Environments section, under Cloud9 IDE, click Open
  1. On the top navigation bar, click File to expand the dropdown menu.
  2. Choose New From Template.
  3. Choose Python File
  1. In the Python code window, type: 
    - print('First code in Cloud9')
  1. On the top navigation bar, click File to expand the dropdown menu.
  2. Choose Save.
  1. In the pop-up box, for Filename, type:<filename.py>
  2. Click Save
  1. On the top navigation bar, click Run.
  2. In the bottom window of the IDE, review the output.
3. Above that window, click the bash terminal tab.
  1. To clone code from an AWS CodeCommit repository, in the bash terminal window, at the command prompt, run (type the command and press Enter):
     - git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/lab
  1. In the left Environment window, click to expand the lab folder.
  2. Open (double-click) the lab_reference.txt file.
  3. In the top lab_reference window, review the file contents.
    - Basic "linux", "git" and, "aws cli" commands, that you might need in this lab, are displayed.
1. In the left Environment window, open (double-click) the hello.py file.
    - The file opens in a new tab.
2. Review the code, and try to understand the flow.
    -The main function execution starts at line 53: def main().
1. To install the required Python modules, in the bottom bash terminal window, at the command prompt, run:
  - sudo pip3 install -r lab/requirements.txt
  - We use Python 3 to run hello.py in this lab.
2. On the top navigation bar, click Run.
3. In the bottom right window, review the output results
1. In the top hello.py window, click in the left gutter at line 57 to add a breakpoint.
2. To view the detailed messages, in the right Details pane, click the Debug Toggler icon.
3. Below the hello.py window, click the Run the Debug Mode icon.
4. On the top navigation bar, click Run. 
  - An arrow sign should appear on the breakpoint.
1. To step through the code until you reach line 61, on the right Details pane toolbar, click the Step Over icon.
2. Under LOCAL VARIABLES, review the values
1. At line 61 in the hello.py code window, on the right Details pane toolbar, click the Step Into icon.
1. Under CALL STACK, review the Function details.
    -These details show the execution stack. In this lab, the generate_banner() function was called inside the main() function at line 61.
2. On the toolbar, click the Step Out icon
1. On the toolbar, click the Step Over icon until line 73.
1. At line 73 in the hello.py code window, on the right Details pane toolbar, click the Step Into icon.
1. On line 25, review the comment, YOUR CODE HERE. 
    - This method has not been implemented yet. Later, you will develop the upload file code yourself. For now, you can improve the code by printing a message about the unimplemented upload function.
2. On the right Details pane toolbar, click Resume
1. At line 57, to delete the set breakpoint, click in the left gutter.
2. At line 76, review the statement: print("Upload Not Implemented Yet")
3. Below the hello.py code window, click the enabled Run in Debug Mode icon to disable it.
4. On the top navigation bar, click Run.
5. In the bottom window, review the output result
1. To create an S3 bucket with an AWS CLI command, in the bottom terminal window, at the command prompt, run:aws s3 mb s3://[YourBucketName]
2. In the top hello.py code window, on line 70, to replace Your_Bucket_Name, type the name of the S3 bucket that you just created.
3. On the top navigation bar, click File to expand the dropdown menu.
4. Choose Save
1. To copy the README file to your S3 bucket, in the bottom terminal window, run: aws s3 cp README.md s3://[your bucket name]
2. To list the objects in your bucket, run: aws s3 ls s3://[your bucket name]
3. To maximize the terminal window, above it, click the resize icon
1. To change to the lab directory, run: cd lab
2. To display your repository and staged changes detail, run: git status
1. To add hello.py to the staging area, run:  git add hello.py 
2. To commit the code to the repository with a comment that describes the code change, run:  git commit -m "Improved upload message" 
3. To update the remote repository, run: git push
1. To return to the previous window size, click the resize icon
1. At the command prompt, run: git status
2. Review to see that the local and remote branches are now in sync.
