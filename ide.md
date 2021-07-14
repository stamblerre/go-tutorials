---
title: Getting Started with Your IDE
description: Exploring your IDE
author: rstambler@google.com
tags: Go
date_published: 
---

# Getting Started with Your IDE

This tutorial will teach you the basics of writing Go code in your IDE.
We will cover structuring your project, writing a function, and testing
and debugging your code.

## Creating your project

### Initializing a module

Let's start by creating a module, which is the unit that defines a Go project.
We can do this through a command, which we can run from the Command Palette. Access the Command Palette by going to the View Menu and selecting "Find Command", or by using the `Ctrl+Shift+P` keyboard shortcut.

<!--Note: This doesn't work yet, because Cloud Shell IDE uses an older version of VS Code Go.-->
Select the `Go: Initialize go.mod` command by typing in the search bar. Enter the module name `example.com` when prompted. Notice that this creates 2 new files in the repository:
<walkthrough-editor-spotlight spotlightId="navigator" spotlightItem="cloudshell_open/go-tutorials/example.com/go.mod">`example.com/go.mod`</walkthrough-editor-spotlight>
and <walkthrough-editor-spotlight spotlightId="navigator" spotlightItem="cloudshell_open/go-tutorials/example.com/go.sum">`example.com/go.sum`</walkthrough-editor-spotlight>.
You can largely disregard the `go.sum` file, but you will refer to the `go.mod` file as you edit your Go project. Let's take a look at it.

### Understanding the `go.mod` file

Let's open the <walkthrough-editor-open-file filePath="cloudshell_open/go-tutorials/example.com/go.mod">`go.mod`</walkthrough-editor-open-file> file for the project.

This is the file defines our project and its dependencies. We are working in the <walkthrough-editor-select-regex filePath="cloudshell_open/go-tutorials/example.com/go.mod" regex='example.com'>`example.com` module</walkthrough-editor-select-regex>, and it is compatible with 
<walkthrough-editor-select-regex filePath="cloudshell_open/go-tutorials/example.com/go.mod" regex='go \d.\d+'>
Go version 1.16
</walkthrough-editor-select-regex>. Note that the Go version declared in the `go.mod` file is not necessarily the Go version you must use--it is the lowest supported version of Go for that module. You can check your current Go version by looking at the Go status bar item in the lower left-hand corner of the editor. <!--Would be nice to highlight the status bar item.-->

### Tidying your module

The `go.mod` file declares the third-party dependencies for the module, and we keep it up to date by tidying our module. The sample project already uses a third-party dependency in the Go code, so let's tidy the module now.

Click the `Run go mod tidy` code lens at the top of the file. <!--Would be nice to highlight the code lens.-->

Once the module is tidied, you will see that the
<walkthrough-editor-select-regex filePath="cloudshell_open/go-tutorials/example.com/go.mod" regex='rsc.io/quote'>`rsc.io/quote` module</walkthrough-editor-select-regex> has been added as a requirement to the `go.mod` file.
This is because a <walkthrough-editor-open-file filePath="cloudshell_open/go-tutorials/example.com/stringutil/quote.go">file in the `stringutil`
</walkthrough-editor-open-file>
package depends on this module already. The <walkthrough-editor-open-file filePath="cloudshell_open/go-tutorials/example.com/go.sum">`go.sum` file</walkthrough-editor-open-file> will also have a corresponding update.

Finally, notice that the additional code lenses now visible in the `go.mod` file. You can use these code lenses to upgrade your dependencies from the editor, without using the command-line.

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

Open the Command Palette by going to the View Menu
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

Type out the following function signature:


```go
func ReverseFile(filename string) (string, error) {}
```

Notice that you are offered autocompletion as you type.

### Read file contents

The first step will be to read in the contents of the file.
Begin typing the following into the body of the function:


∂Type the following in the function body:

```go
    contents, err := os.
```

Notice the autocompletion result
and accept the autocompletion results. The "os" package will be automatically imported into your file.

<walkthrough-editor-spotlight spotlightId="menu-terminal-new-terminal">New Terminal</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="navigator" spotlightItem="go.mod">go.mod file</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-file">File Menu</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-run">Run menu</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-run-start-without-debugging">Start without debugging</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="debug-configuration">Debug configuration panel</walkthrough-editor-spotlight>
<walkthrough-editor-spotlight spotlightId="menu-run-start-without-debugging">Start without debugging</walkthrough-editor-spotlight>
