# web-archive-replay

[web-archive-replay](https://github.com/evanwill/web-archive-replay) is a basic template repository to create a self-contained, stand alone site to access web archive captures using Jekyll on GitHub Pages (or where every you want to host it).
Powered by [ReplayWeb.page](https://replayweb.page/docs/embedding).

Demo:

## Get Started 

From https://github.com/thecdil/bootstrap5-template 

- Click green "Use this template" button to make a copy of the code in your own repository (alternatively, use Import or manually copy files)
- Edit `_config.yml` with your site information
- In your new repository visit "Settings" > "Pages" to activate GitHub Pages
- Edit and create pages in the "pages" folder (probably in Markdown). Use each page's yaml front matter to populate the navbar:
    - `title` will appear as h1 at top of the page content.
    - `nav` if this option has a value, it will appear in the navbar as link to this page.
    - `nav_order` navbar items will be sorted using this number. 
- Use "includes" to simplify adding Bootstrap features to Markdown pages (see comments in the "_include/" files for instructions).

See [docs/create-website.md](https://github.com/thecdil/bootstrap5-template/blob/main/docs/create-website.md) for more details.

## Customize 

- Tweak base variables in `assets/css/main.scss` (text color, link color, container size)
- Tweak bootstrap theme colors using `_data/theme-colors.csv` (add a css color in the color column next to the BS color-class to override, or create a new class name. This will generate btn-, text-, and bg- classes.)
- Add custom CSS to `_sass/_custom.scss` (content of `_sass/_template.scss` relates to template components)
- Use Bootstrap to customize `_layouts/` and `_includes/template/`.

## Template Assets

Included in assets/lib folder:

- [ReplayWeb.page](https://github.com/webrecorder/replayweb.page/)
- [Bootstrap](https://getbootstrap.com/docs/5.1/getting-started/introduction/) 5.2
- [Bootstrap Icons](https://icons.getbootstrap.com/) 1.9
- [lunr.js](https://lunrjs.com/) 2.3.9
- [lazysizes](https://github.com/aFarkas/lazysizes) 5.3.2
