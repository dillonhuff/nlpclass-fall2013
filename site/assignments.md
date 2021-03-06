---
layout: default
title: Assignment Requirements
---

## Overview

This page describes the expectations for how you will prepare your coding assignments and submit them for grading.




## GitHub

Your code should be hosted in a *private* GitHub repository.  Follow these instructions:

1. If you do not have an account on GitHub, you need to create one here: [github.com](https://github.com/).
2. Register as a student here: [github.com/edu](https://github.com/edu).  This will give you five free private repositories, one of which will be used for this class.
3. Create a new repository for your classwork called 
    {% highlight text %}nlpclass-fall2013-lastname-firstname{% endhighlight %}
    by clicking on "New Repository" on the GitHub website.  Be sure to select ***PRIVATE*** repository.
4. Add me as a "collaborator".  Do this from the GitHub webpage for your repository: `Settings` `->` `Collaborators` `->` `Add a friend` and enter my username: `dhgarrette`.  Do the same for Lewis's username: `lewfish`.
5. Clone your repositiory.
    {% highlight text %}$ git clone git@github.com:USERNAME/REPOSITORY-NAME.git{% endhighlight %}
6. Follow the instructions on the [Scala Environment Setup]({{ page.root }}scala/setup.html) page to create a scala project in your repository directory.
7. Create a file `.gitignore` in the root of your repository that contains this:

		*.class
		*.log
		.DS_STORE

		# sbt specific
		dist/*
		target/
		lib_managed/
		src_managed/
		project/boot/
		project/plugins/project/

		# Scala-IDE specific
		.scala_dependencies
		.classpath
		.project
		.settings/
		.cache

8. Add the following to your main `build.sbt`:
    {% highlight text %}
resolvers ++= Seq(
  "dhg releases repo" at "http://www.cs.utexas.edu/~dhg/maven-repository/releases",
  "dhg snapshot repo" at "http://www.cs.utexas.edu/~dhg/maven-repository/snapshots"
)
    
libraryDependencies += "com.utcompling" % "nlpclass-fall2013_2.10" % "0001" changing(){% endhighlight %}

    This creates a dependency from your project to the course project code, which exists online.  I will use this project to provide code to you that your code can access.

    If you use Eclipse, then you will need to re-run `sbt "eclipse with-source=true"` and refresh the project from within Eclipse before you will see the changes.

    Whenever I update this dependency, I will push a new version online with a new version number.  The first version number is `0001`, and I will tell you each time I increment it.  When I do, you will have to correspondingly update the number in this file.


## Assignment Code

The code for your assignments will be "turned in" via your GitHub repo.  You should probably develop it there too (and you should definitely not develop it in a *public* repository!).

For each assignment, I will give you instructions on what to call certain classes, but the rest of the structure of your up to you.  You will, however, have to document the files used in a README for each assignment to make grading easier.

The way that you will "turn in" you code is:
1. Check your code in to GitHub and "push" it so that it is visible to us.
2. Email both me (dhg@cs.utexas.edu) and Lewis (lewfish@cs.utexas.edu) to tell us that your code is ready to grade.  Each assignment will have specific text for  you to use as the subject of your email.  It will be in this form (where *a0* is for assignment 0 and *a1* would be for assignment 1, etc):
  
> nlpclass-fall2013 a0 completed lastname firstname

We will grade based on the latest commit of your code up to the deadline unless you specifically tell us to grade a different commit.
