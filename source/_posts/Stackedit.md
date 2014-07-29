title: 'Giving stackedit a try'
date: 2014-07-26 18:59:18
tags:
---
 
A new online markdown editor	
=====================

This is my very first post written using [StackEdit](https://stackedit.io/), a free, open-source Markdown editor based on PageDown, the Markdown library used by Stack Overflow and the other Stack Exchange sites.

----------


Documents
---------

**StackEdit** stores the documents in the browser local storage, which means they are are automatically saved locally and are accessible offline.

> **NOTE:** This also means that the documents are not shared between different browsers or computers and that clearing my browser's data may **delete all of them!**

#### <i class="icon-file"></i> Create a document

You can create a new document by clicking the <i class="icon-file"></i> button in the navigation bar. This will switch from the current document to the new one.

#### <i class="icon-folder-open"></i> Switch to another document

You can as well list all your local documents and switch from one to another by clicking the <i class="icon-folder-open"></i> button in the navigation bar.

#### <i class="icon-pencil"></i> Rename a document

You can rename the current document by clicking the document title in the navigation bar.

#### <i class="icon-trash"></i> Delete a document

You can delete the current document by clicking the <i class="icon-trash"></i> button in the navigation bar.

#### <i class="icon-hdd"></i> Save a document

You can save the current document to a file using the <i class="icon-hdd"></i> `Save as...` sub-menu.

> **NOTE:** See [<i class="icon-share"></i> Publish a document](#publish-a-document) section for a description of the different outputs.


----------


Synchronization
---------------

**StackEdit** can be combined with **Google Drive** and **Dropbox** to have your documents centralized in the *Cloud*. The synchronization mechanism will take care of uploading your modifications or downloading the latest version of your documents.

> **NOTE:**
> 
> - Full access to **Google Drive** or **Dropbox** is required to be able to import any document in StackEdit.
> - Imported documents are downloaded in your browser and are not transmitted to a server.
> - If you experience problems exporting documents to Google Drive, check and optionally disable browser extensions, such as Disconnect.

#### <i class="icon-download"></i> Import a document

You can import a document from the *Cloud* by going to the <i class="icon-provider-gdrive"></i> `Google Drive` or the <i class="icon-provider-dropbox"></i> `Dropbox` sub-menu and by clicking `Import from...`. Once imported, your document will be automatically synchronized with the **Google Drive** / **Dropbox** file.

#### <i class="icon-upload"></i> Export a document

You can export any document by going to the <i class="icon-provider-gdrive"></i> `Google Drive` or the <i class="icon-provider-dropbox"></i> `Dropbox` sub-menu and by clicking `Export to...`. Even if my document is already synchronized with **Google Drive** or **Dropbox**, you can export it to a another location. **StackEdit** can synchronize one document with multiple locations.

#### <i class="icon-refresh"></i> Synchronize a document

Once your document is linked to a **Google Drive** or a **Dropbox** file, **StackEdit** will periodically (every 3 minutes) synchronize it by downloading/uploading any modification. Any conflict will be detected, and a local copy of your document will be created as a backup if necessary.

If you just have modified your document and you want to force the synchronization, click the <i class="icon-refresh"></i> button in the navigation bar.

> **NOTE:** The <i class="icon-refresh"></i> button is disabled when:
> 
> - You are offline,
> - or the document is not synchronized with any location,
> - or the document has not been modified since the last synchronization.

#### <i class="icon-refresh"></i> Manage document synchronization

Since one document can be synchronized with multiple locations, you can list and manage synchronized locations by clicking <i class="icon-refresh"></i> `Manage synchronization` in the <i class="icon-provider-stackedit"></i> menu. This will open a dialog box allowing you to add or remove synchronization links that are associated to your document.

> **NOTE:** If you delete the file from **Google Drive** or from **Dropbox**, the document will no longer be synchronized with that location.

----------


Publication
-----------

Once you are happy with your document, you can publish it on different websites directly from **StackEdit**. As for now, **StackEdit** can publish on **Blogger**, **Dropbox**, **Gist**, **GitHub**, **Google Drive**, **Tumblr**, **WordPress** and on any SSH server.

#### <i class="icon-share"></i> Publish a document

You can publish your document by going to the <i class="icon-share"></i> `Publish on` sub-menu and by choosing a website. In the dialog box, you can choose the publication format:

- Markdown, to publish the Markdown text on a website that can interpret it (**GitHub** for instance),
- HTML, to publish the document converted into HTML (on a blog for instance),
- Template, to have a full control of the output.

> **NOTE:** The default template is a simple webpage wrapping my document in HTML format. You can customize it in the `Services` tab of the <i class="icon-cog"></i> `Settings` dialog.

#### <i class="icon-share"></i> Update a publication

After publishing, **StackEdit** will keep your document linked to that publish location so that you can update it easily. Once you have modified your document and you want to update my publication, click on the <i class="icon-share"></i> button in the navigation bar.

> **NOTE:** The <i class="icon-share"></i> button is disabled when:
> 
> - You are offline,
> - or the document has not been published anywhere.

#### <i class="icon-share"></i> Manage document publication

Since one document can be published on multiple locations, you can list and manage publish locations by clicking <i class="icon-share"></i> `Manage publication` in the <i class="icon-provider-stackedit"></i> menu. This will open a dialog box allowing you to remove publication links that are associated to your document.

> **NOTE:** In some cases, if you remove the file from the website or the post from the blog, the document will no longer be published on that location.

----------


Markdown Extra
--------------

**StackEdit** supports **Markdown Extra**, which extends **Markdown** syntax with some nice features.

> **NOTE:** You can disable any **Markdown Extra** feature in the `Extensions` tab of the <i class="icon-cog"></i> `Settings` dialog.


### Tables

**Markdown Extra** has a special syntax for tables:

Item      | Value
--------- | -----
Computer  | $1600
Phone     | $12
Pipe      | $1

You can specify column alignment with one or two colons:

| Item      |  Value | Qty  |
| :-------- | ------:| :--: |
| Computer  | $1600 |  5   |
| Phone     |   $12 |  12  |
| Pipe      |    $1 | 234  |


### Definition Lists

**Markdown Extra** has a special syntax for definition lists too:

Term 1
Term 2
:   Definition A
:   Definition B

Term 3

:   Definition C

:   Definition D

	> part of definition D


### Fenced code blocks

GitHub's fenced code blocks are also supported with **Prettify** syntax highlighting:

```
// Foo
var bar = 0;
```

> **NOTE:** To use **Highlight.js** instead of **Prettify**, just configure the `Markdown Extra` extension in the <i class="icon-cog"></i> `Settings` dialog.


### Special Attributes

With **Markdown Extra**, you can specify `class` and `id` attributes on headers and fenced code blocks just like this:

##### Header example 

``` 
var foo = bar;
```


  [1]: http://math.stackexchange.com/
  [2]: http://daringfireball.net/projects/markdown/syntax "Markdown"
  [3]: https://github.com/jmcmanus/pagedown-extra "Pagedown Extra"
  [4]: http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference
  [5]: https://code.google.com/p/google-code-prettify/
  [6]: http://highlightjs.org/
  