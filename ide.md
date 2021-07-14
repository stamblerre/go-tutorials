---
title: Getting Started with Your IDE
description: Exploring your IDE
author: rstambler@google.com
tags: Go
date_published: 
---

# Getting Started with Your IDE

This is a great tutorial!

## Initialize a `go.mod` file

Should we do this part in the tutorial?

## Open a `go.mod` file

Let's start by <walkthrough-editor-open-file filePath="cloudshell_open/go-tutorials/example.com/go.mod">opening the go.mod</walkthrough-editor-open-file> file for the project.

This file defines our project. We are working in the

<!--TODO(rstambler): Switch to using regexes here.-->
<walkthrough-editor-select-line filePath="cloudshell_open/go-tutorials/example.com/go.mod"
    startLine="0" startCharacterOffset="7"
    endLine="0" endCharacterOffset="19">
`example.com` module
</walkthrough-editor-select-line>, and we are developing with

<!--TODO(rstambler): Switch to using regexes here.-->
<walkthrough-editor-select-line filePath="cloudshell_open/go-tutorials/example.com/go.mod"
    startLine="2" startCharacterOffset="0"
    endLine="2" endCharacterOffset="8">
Go version 1.16
</walkthrough-editor-select-line>.

## Run `go mod tidy`

Click the `Run go mod tidy` code lens at the top of the file. (How can we highlight a code lens?)

<!--TODO(rstambler): Switch to using regexes here.-->
Note that the
<walkthrough-editor-select-line filePath="cloudshell_open/go-tutorials/example.com/go.mod"
    startLine="4" startCharacterOffset="8"
    endLine="4" endCharacterOffset="21">
`rsc.io/quote` module
</walkthrough-editor-select-line> has been added to the `go.mod` file.
This is because a

<walkthrough-editor-open-file filePath="cloudshell_open/go-tutorials/example.com/stringutil/quote.go">
file in the `stringutil`
</walkthrough-editor-open-file>

package depends on this module already.

Any third-party dependencies in your code must be declared in your `go.mod` file.

Notice that there are now additional code lenses shown in the `go.mod` file.
You can use these code lenses to upgrade your dependencies from the editor, without using the command-line.

## Let's start writing some Go code

We're going to work on a function to reverse a string.
We'll start from our test case, which you can see in

<walkthrough-editor-open-file filePath="cloudshell_open/go-tutorials/hello.txt">
this `hello.txt` file
</walkthrough-editor-open-file>.

We're going to write the code to reverse the contents of this file.

### Symbol search

We already have a function that reverses a string somewhere in this project,
so let's use workspace symbol search to find it.

Open the Command Palette by going to the
<walkthrough-editor-spotlight spotlightId="menu-view">View Menu</walkthrough-editor-spotlight>
and selecting "Find Command", or by using the `Ctrl+Shift+P` keyboard shortcut.

Delete the `>` character in the box. That character indicates that you will search for available commands.
Type the `#` symbol to indicate that you are doing a workspace symbol search.
You can use the `@` symbol to start a search for symbols only in the current file.
Then, type your search keyword. In this case, it is "reverse".

The first result should be in the

<walkthrough-editor-open-file filePath="cloudshell_open/go-tutorials/example.com/stringutil/reverse.go">
`reverse.go`
</walkthrough-editor-open-file>.

Select that result and go to the function definition.

## Writing a new function

Let's write a new function, which we will call `ReverseFile`.

<walkthrough-editor-spotlight spotlightId="menu-terminal-new-terminal">New Terminal</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="navigator" spotlightItem="go.mod">go.mod file</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-file">File Menu</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-run">Run menu</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-run-start-without-debugging">Start without debugging</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="debug-configuration">Debug configuration panel</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-run-start-without-debugging">Start without debugging</walkthrough-editor-spotlight>
