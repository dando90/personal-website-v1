# Personal Website — Version 1

This repository contains the source code for the first version of my personal website. It was a static portfolio site introducing me and bringing together information about my background, skills, and contact details.

This version is preserved as an archived project and remains available at <https://www.stefanochiabrando.com/projects/personal-website-v1/>. The repository contains the original source code for this version.

## Pages

- **Home** — introduction and personal profile
- **About** — background and biography
- **Skills** — skills overview
- **Portfolio** — portfolio page from this version of the site
- **Contact** — contact and social links

## Technologies

- **HTML5** for page structure and content
- **CSS3** for layout, responsive styling, and presentation
- **Sass (SCSS)** for the stylesheet source files in `assets/sass/`
- **JavaScript** for the rotating introduction text on the home page
- **SVG** for interface icons and some illustrations
- **Web fonts** served locally from `assets/font/`

The compiled stylesheets are already included in `assets/css/`, so Sass or any other build tool is not required to run the site.

## Run locally

You can serve the files with any static web server. A server is recommended because the site uses root-relative paths such as `/assets/...`.

### Node.js

If you have Node.js installed, you can use `npx` to start a static server:

```bash
npx serve .
```

Open the local URL printed in the terminal.

## Repository structure

```text
.
├── index.html              # Home page
├── about/index.html        # About page
├── skills/index.html       # Skills page
├── portfolio/index.html    # Portfolio page
├── contact/index.html      # Contact page
└── assets/
    ├── css/                # Compiled stylesheets
    ├── font/               # Locally hosted web fonts
    ├── img/                # Images, icons, and illustrations
    └── sass/               # SCSS source files
```

## Compile Sass to CSS

The editable Sass sources are in `assets/sass/`, while the HTML pages load the compiled files in `assets/css/`. To rebuild the stylesheets, install Sass if needed and run the following from the repository root:

```bash
npx sass --style=compressed --no-source-map \
  assets/sass/style.scss:assets/css/style.min.css \
  assets/sass/home.scss:assets/css/home.min.css \
  assets/sass/about.scss:assets/css/about.min.css \
  assets/sass/skills.scss:assets/css/skills.min.css \
  assets/sass/portfolio.scss:assets/css/portfolio.min.css \
  assets/sass/contact.scss:assets/css/contact.min.css
```

If Sass is not already available, `npx` will offer to download it for this run. Alternatively, install it globally with `npm install --global sass` and replace `npx sass` with `sass` in the command. The `_config.scss` file contains shared Sass configuration and is imported by the page stylesheets; it is not compiled on its own.
