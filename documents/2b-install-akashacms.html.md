---
layout: page.html.ejs
title: Installing AkashaCMS, AkashaEPUB
---


Now that Node.js and Grunt are installed we can follow the instructions to install AkashaCMS.  As we said, AkashaCMS is a "content management system" which basically means builds an HTML website from a bunch of documents.  As we'll see, an EPUB file is also a cluster of HTML files, and AkashaEPUB simply adapts AkashaCMS to building HTML and XML files required for an EPUB. -

See [akashacms.com/install.html](http://akashacms.com/install.html) for more details on how to install AkashaCMS.

```
    $ npm install -g akashacms
    $ akashacms init akashacms-example
    $ cd akashacms-example
    $ npm install
    $ akashacms build
    $ akashacms preview
```

That first step might need to be done this way, if you get an error message:

```
    $ sudo npm install -g akashacms
```

It's useful to glance through the `akashacms-example` directory just created and take a look at the configuration file and other files.

## Installing AkashaEPUB

You don't install AkashaEPUB separately.  Instead, it's installed as a plugin to an AkashaCMS workspace, in the AkashaCMS `config.js`.

To make it easier to get started with AkashaEPUB, a skeleton book has been created in the [github.com/akashacms/epub-skeleton](https://github.com/akashacms/epub-skeleton) repository.  It has all the basic elements of a "book" including a book cover image (of a skeleton).

```
    $ git clone https://github.com/akashacms/epub-skeleton.git
    $ mv epub-skeleton newBookName
    $ cd newBookName
    $ npm install
```

Notice that when you ran `npm install` both `akashacms-epub` and `grunt` were downloaded and installed in the `node_modules` directory.  You can verify the Grunt installation as so

```
    $ grunt --version
    grunt-cli v0.1.13
```

And, for the impatient among you, you can build the `skeleton.epub` like so:

```
    $ grunt doepub
    [2015-04-14 19:28:15.998] [INFO] epub - akashacms-epub
    Running "useEPUBStylesheets" task
    
    Running "emptyRootOut" task
    [2015-04-14 19:28:16.188] [INFO] akashacms - removing out
    [2015-04-14 19:28:16.193] [INFO] akashacms - making empty out
    ... mucho output
    Running "bundleEPUB" task
    [2015-04-14 19:28:16.845] [INFO] epub - 124034 total bytes
    [2015-04-14 19:28:16.845] [INFO] epub - archiver has been finalized and the output file descriptor has closed.
    
    Done, without errors.
```

You can then open `skeleton.epub` with an EPUB reader and view your handiwork.