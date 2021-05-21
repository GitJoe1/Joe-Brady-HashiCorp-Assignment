# Working with Git and GitLab Locally

GitLab is a Git hosting platform service that organizations use to provide management of Git repositories.  GitLab has developed a lifecycle tracking tool that provides a Git repository manager for hosting code.  It also offers issue-tracking and CI/CD features.  GitLab helps teams collaborate and build software, fundamentally changing the way Development, Security, and Ops teams work together. 

## Upon Completion of this guide, Learners will be able to:

1. Discuss Git as a solution, and what problems it solves.  
1. Describe the benefits of DevOps.  
1. List most common Git commands.  
1. Explain basic Git mechanisms at a high level.  

## Prerequisites

For a successful learning engagement, we recommend the following before starting:  

1. Registering and signing into your Git account.  For help, follow the instructions here: https://about.gitlab.com/services/education/prereq/

2. Opening well-known ports SSH (port 22) and HTTPS (Port 443) in order to access your lab environment.

3. Generating SSH keys.  For help, follow the instructions here: https://docs.gitlab.com/ee/ssh/

## Configure Git Locally
In this section of the lab guide, you will Install Git locally, generate an SSH key, add the generated SSH key to the GitLab platform, and clone an existing repository to your local machine.

## Step 1: Verify Git Is Installed
Open a terminal window, enter `git version`, and press enter.

![Screen Shot 2021-05-20 at 7 55 13 PM](https://user-images.githubusercontent.com/26533339/119062638-4f883100-b9a5-11eb-81e0-9bf1383126ec.png)  

## Step 2: Generate An SSH Key 
In your terminal window, enter `ssh-keygen` and press enter.  Accept the defaults; you do not need to enter a passphrase.

![Screen Shot 2021-05-20 at 7 58 58 PM](https://user-images.githubusercontent.com/26533339/119062905-d2a98700-b9a5-11eb-9dd7-13bcb68861a3.png)  

## Step 3: Copy Your SSH Public Key
Change into your hidden `.ssh` directory to view the newly-generated files:  

```
cd ~/.ssh  
ls –al  
```

![Screen Shot 2021-05-20 at 8 00 31 PM](https://user-images.githubusercontent.com/26533339/119062997-097f9d00-b9a6-11eb-855e-e19fb66540e5.png)  

Note: `id_rsa_customer` and `id_rsa_customer.pub` are the private and public keys, respectively.  

Open a new web browser window and log into your GitLab account.  Once logged in, navigate to the top right corner of your dashboard. Click on the `Users` icon, then `Settings`, navigate to `SSH Keys` in the left pane, and expand the `SSH Key` dialog box.  

Paste the key into the open text field (Command-V on macOS or Control-V on Windows), and click the `Add Key` button.

![Screen Shot 2021-05-20 at 8 02 54 PM](https://user-images.githubusercontent.com/26533339/119063146-5ebbae80-b9a6-11eb-8baa-e2e1c60e6d16.png)  

Your local computer is now authenticated to push and pull (interact) with GitLab!  

## Step 4: Copy (Clone) Your Repository To Your Local Machine

Navigate back to your GitLab dashboard. Click the `Clone` button and copy the `Clone with SSH` URL.

![Screen Shot 2021-05-20 at 8 10 29 PM](https://user-images.githubusercontent.com/26533339/119063559-6def2c00-b9a7-11eb-8378-949f5660ed16.png)  

## Step 5: Clone Your Repository

In your terminal window, create a new Training directory in your home directory:    

```
mkdir ~/Training
cd ~/Training
```

Run `git clone <URL you previously copied>`:

![Screen Shot 2021-05-20 at 8 13 29 PM](https://user-images.githubusercontent.com/26533339/119063749-d9d19480-b9a7-11eb-8e30-6dd3f94feb0a.png)

Your repository has now been locally cloned and you’re ready to get to work!  

## Summary
In this section, you have verified that Git was installed and available on your local computer.  You created an SSH public key for authenticating and transferring files between your local machine and the GitLab platform.  You then added your public key to the GitLab platform and cloned your repository to your local machine, to interact with Git and GitLab locally.  In the next section, you will make changes to a file on your local machine and “push” them to the Git service hosted on GitLab.

For additional information and documentation:
https://git-scm.com/docs
