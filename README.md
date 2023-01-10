# web-archive-replay

*This is a demo proof of concept project!*

[web-archive-replay](https://github.com/evanwill/web-archive-replay) is a basic template repository to create a self-contained site providing access to web archive captures, using Jekyll on GitHub Pages (or where every you want to host it), powered by [ReplayWeb.page](https://replayweb.page/docs/embedding).
This allows you to sustainably publish a curated web archive along side contextual information as a stand alone digital exhibit website.

Demo: <https://evanwill.github.io/web-archive-replay/>

## Get Started 

See "docs/setup-web-archive.md" for details of web archive interface. 

Basic site set up:

- Click green "Use this template" button to make a copy of the code in your own repository (alternatively, use Import or manually copy files)
- Edit `_config.yml` with your site information
- In your new repository visit "Settings" > "Pages" to activate GitHub Pages
- Edit and create pages in the "pages" folder (probably in Markdown). Use each page's yaml front matter to populate the navbar:
    - `title` will appear as h1 at top of the page content.
    - `nav` if this option has a value, it will appear in the navbar as link to this page.
    - `nav_order` navbar items will be sorted using this number. 
- Use "includes" to simplify adding Bootstrap features to Markdown pages (see comments in the "_include/" files for instructions).

See [docs/create-website.md](https://github.com/thecdil/bootstrap5-template/blob/main/docs/create-website.md) for more details.

## Template Assets

Included in assets/lib folder:

- [ReplayWeb.page](https://github.com/webrecorder/replayweb.page/)
- [Bootstrap](https://getbootstrap.com/docs/5.1/getting-started/introduction/) 5.2
- [Bootstrap Icons](https://icons.getbootstrap.com/) 1.9
- [lunr.js](https://lunrjs.com/) 2.3.9
- [lazysizes](https://github.com/aFarkas/lazysizes) 5.3.2
