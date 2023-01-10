# Setup Web Archive replay access

The web-archive-replay template uses [ReplayWeb.page embedding](https://replayweb.page/docs/embedding) to provide access to a web archive file (WACZ or WARC format) in a completely self-contained static web project.
All necessary dependencies are included in the template so that you do not have to rely on 3rd party CDNs or APIs.
This allows you to sustainably publish a curated web archive along side contextual information as a digital exhibit website.

The template builds on [bootstrap5-template](https://github.com/thecdil/bootstrap5-template)--see "docs/create-website.md" for details on setting up and customizing the basic website. 

## Prep Web Archive

There are many tools used to capture a web archive--this template supports any archive stored in WACZ or WARC format.
If you are interested in interactively creating a curated web archive, try [ArchiveWeb.page](https://webrecorder.net/tools#archivewebpage), a Chrome extension and desktop app developed by [Webrecorder](https://webrecorder.net/).
The tool allows you to surf through web pages capturing as you browse, enabling high quality archives.
Learn more by reading the [ArchiveWeb.page Guide](https://archiveweb.page/guide).
To export your ArchiveWeb.page archive, click the extension's home icon, and click the download icon on the archive's record.
Your archive will be saved as a WACZ file, look for the `.wacz` extension.

Copy your `.wacz` or `.warc` archive file into your project's "archives" folder. 
The template contains an example, "archives/demo-archive.wacz".

If you are storing the project on GitHub, keep in mind the storage limits--your archives should probably not be over 500 MB unless you set up LFS or some other solution.

## Add Web Archive to a Page

To display the ReplayWeb.page access interface on your website, you will edit one of the content pages of the site. 
The template includes the demo "pages/example.md".

to set up the page you will add two keys to the YAML front matter:

- add `layout: web-archive`
- add `archive: ` plus the full filename of your web archive file in the "archives" folder or the full URL to an archive hosted elsewhere. e.g. `archive: demo-archive.wacz` or `archive: https://replayweb.page/docs/assets/tweet-example.wacz`

The front matter will look like: 

```
---
title: Example Web Archive
nav: Example
nav_order: 1
layout: web-archive
archive: demo-archive.wacz
---
```

Any markdown content on this page will display above the ReplayWeb.page interface.
