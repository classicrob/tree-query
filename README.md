# `tree-query`

> This README is TODO. If you'd like to use this software in a project, **don't hestiate to reach out to me.**

Tree query is a tool that searches across indented lines.

It is a replacement for Roam's query system. It supports everything Roam does, except for block references.

## Quickstart

**Query in current directory:**
```
tree-query '{and: [[Page 1]] [[Page 2]]}' .
```
[*Learn to navigate to a working directory with `cd`*](https://linuxize.com/post/linux-cd-command/)

**Query in a folder:**
```
tree-query '{and: [[Page 1]] [[Page 2]]}' /Users/steve/myfoldername/
```
*Learn to get the location of a folder on [macOS](https://osxdaily.com/2009/11/23/copy-a-files-path-to-the-terminal-by-dragging-and-dropping/), [Windows](https://www.top-password.com/blog/copy-full-path-of-a-folder-file-in-windows/), or [GNU+Linux](https://unix.stackexchange.com/questions/102551/mouse-shortcut-to-copy-the-path-to-a-file-in-the-gnome-file-manager).*

Or query in multiple folders and files:

```
tree-query '{and: [[Page 1]] [[Page 2]]}' /Users/steve/myfoldername/ file1
```

**Query stdin with pipes:**
```
cat myfile | tree-query '{and: [[Page 1]] [[Page 2]]}'
```
[*Learn to build powerful no-code applications using pipes*](https://youtu.be/tc4ROCJYbm0?t=360)

## Features

This section is a work-in-progress.

* **Fast**

## Basic usage with the command-line

### Copy result to clipboard
macOS:
```
tree-query '{and: [[Page 1]] [[Page 2]]}' . | pbcopy
```

GNU+Linux:
```
tree-query '{and: [[Page 1]] [[Page 2]]}' . | 
```

## Contributing

Tree-query is written in [Dlang](https://dlang.org) but don't let that put you off- if you know C, C++, or Java, you'll pick it up very quickly.

If you have any questions on D, feel free to go to #d on freenode or D Forums. People are very nice.

### Internals

I've spent some time writing doc comments inside the code. They provide a conceptual explanation of how the system works. Look for `/**` and `/++`.

Inside the unittests, there's an example guide on using `parser.d` as a library to build a Markdown to XML converter. 

### Notes

A string in D is a reference to a region of immutable memory. It is a length and a pointer. For this reason, it is is very efficient to copy.

A struct is like a Java record or class.

## Known bugs
 - Mixing tabs and spaces is not supported, unless an explicit spaces per indent specified
