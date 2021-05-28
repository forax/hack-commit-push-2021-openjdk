# hack-commit-push-2021-openjdk
The repository with the information about the session about patching the OpenJDK at hack-commit-push 2021

  https://hack-commit-pu.sh/

## During the event

During the virtual event, i will be available on the conference session
and on the slack of hack-commit-push, channel #proj-openjdk

Don't hesitate to join, say hello, ask questions, provide answers, etc

# So you want to patch the source of the JDK :)

The source of the JDK are stored on Github, the main repository is at
  
  https://github.com/openjdk/jdk

## Create a Github acount

Before patching the JDK, the first step is to first clone the JDK repository to your own
repository on github, so
- create a github account if you do not have one
  
  https://github.com/join
  
  add your public SSH key to your account, so Github knows that you are the one pushing code via git
  
  https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
  
  if you don't have one, don't worry the instructions also explain how to create a SSH key
  
- fork the OpenJDK/jdk repository into you own repository
  there is a button "fork" on the https://github.com/openjdk/jdk for that
  
- use your favorite IDE to clone your repository to a local folder
  The "git address" of the github repository is available using the green dropdown button "clone",
  and then select the SSH version

  - with IntelliJ, it's File > New > Project from version control, then
    copy the line (that should start with "git@...")
    
  - on a terminal, it's just `git clone` with the address of the forked repository
    ```
    git clone git@...
    ```

## Build the JDK

Now you need to build the JDK from the source on your local repository, the instruction
are available here
  https://github.com/openjdk/jdk/blob/master/doc/building.md
  
While it's building, we have the time to look for a bug to fix, i say a bug, but the best
is not to start with an actual bug in the code but just a javadoc bug fix

## Sign the Oracle Contributor Agreement (OCA)

First you need to sign the Oracle contributor Agreement, It's a single page document
  https://oca.opensource.oracle.com/

  This is how the London Java User Group describes the OCA:
  - If you’re working on Open JDK and your work is approved for submission you will need to have one of these.
  - The essence of this agreement is to share the ownership of the change between yourself and Oracle.
  - If you’re thinking about taking this path it’s only a simple one page document that is quick to complete, so I recommend doing this upfront. 
  - If you are going through your employers approval process it is potentially a good idea to try get both of these agreements signed off at the same time if you need to.

  Sadly, there is no workaround the OCA, even if it's for a very small contribution, you have to sign the OCA.

## Find a spec bug in the bug database

Crawling the bug database to find a javadoc issue to fix
The bug database is available here (yes, it's JIRA so it's slooow)
  
  https://bugs.openjdk.java.net/

The magic keyword to get the documentation issue is "spec", and you also need to filter
to only get the _open issues_, it's the third dropdown menu from the left, select OPEN.

If you want to restrict yourself to particular are of the JDK, in More, you can add the dropdown "component",
and by example for java-base (java.lang, java.util, etc) select core-libs.

## Add an issue in this repository

Once you have found a spec issue you want to fix, add an issue in this repository to let know
the other participant of hack-commit-push that you want to fix that issue.
  
  https://github.com/forax/hack-commit-push-2021-openjdk/issues


## Subscribe to the OpenJDK mailing lists

You also need to subscribe to the mailing lists.
Being a subscriber of the mailing list, let you see all the patch and discussion around those patch.
There is one mailing list by component of the JDK, all the mailing lists are available at
  
  https://mail.openjdk.java.net/mailman/listinfo

By example, the mailing list for java.base (java.lan, java.util) etc is
  
  https://mail.openjdk.java.net/mailman/listinfo/core-libs-dev


## Create the pull request

Once you have fixed the issue in your local repository, your ready to create a pull request (PR)
You can create a PR even if you have not signed yet the OCA but it will never be integrated
without signing the OCA.

To create a pull request, in your repository that clone `openjdk/jdk`, the is a tab named "Pull request",
the second tab from the left, from that tab you can create a pull request,
i.e. ask people to review you change in order to be integrated in the JDK.
So click on "create pull request".

The OpenJDK github repositories use bots to links the pull request (PR) with the other parts, the bug issues, etc
Here is a list of all 
  
  https://wiki.openjdk.java.net/display/SKARA/Pull+Request+Commands

With that you should be able to link your pull request to the corresponding bug in the database.

Once you have signed the OCA, your change will be reviewed and integrated or not after discussions.
