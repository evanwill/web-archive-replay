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
Note, [WACZ](https://specs.webrecorder.net/wacz/latest/) is preferred format that is specifically designed for this use case, allowing very efficient access to the index and contents of the archive without forcing the user to download the entire file.
You can use the [py-wacz](https://github.com/webrecorder/py-wacz) utility to repackage existing WARC files into WACZ format.

If you are storing the project on GitHub, keep in mind the [storage limits and file size limits](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github#file-size-limits)--your archives should probably not be over 500 MB unless you set up LFS or some other solution.

Alternately, you can host your WACZ file in some other web location that has CORS enabled (e.g. AWS, Zenodo).
For example, if you upload your WACZ to Zenodo, your item will have a main page like "https://zenodo.org/record/6390157".
Scroll down and click on "JSON" under the Export options to view the detailed metadata, e.g. "https://zenodo.org/record/6390157/export/json". 
Look in the object "files" > "links" > "self" for the URL using the file API, e.g. "https://zenodo.org/api/files/88a7020c-f61e-4d00-89ba-c000dbc23b5e/test.wacz".
Use this URL to add the archive to your display page.
*Note: Zenodo probably does not work other than for a demo as the file API seems to have a rate limit--to avoid downloading the full file, ReplayWeb.page does bunches of tiny requests, which seems to trigger the rate limit...*

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
