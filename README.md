# Puzzle ITC Revealjs Theme

![Puzzle ITC Revealjs Theme](demo.png)

Revealjs Dokumentation: https://github.com/hakimel/reveal.js

## Usage with reveal-md
### Global
1. Install reveal-md: `sudo npm install -g reveal-md`
2. Open the presentation:

    ```reveal-md demo.md --watch --theme https://ghcdn.rawgit.org/puzzle/pitc-revealjs-theme/1.0.2/theme/puzzle.css```

Optional: Add an alias in your `.bashrc`:
```
alias reveal-md='reveal-md --watch --theme https://ghcdn.rawgit.org/puzzle/pitc-revealjs-theme/master/theme/puzzle.css'
```

### Local (per project)
1. Install reveal-md: `npm install --save reveal-md`
2. Add script in your `packages.json`:

    ```
    ...
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "reveal-md": "reveal-md demo.md --watch --theme https://ghcdn.rawgit.org/puzzle/pitc-revealjs-theme/1.0.2/theme/puzzle.css"
    },
    ...
    ```
3. Open the presentation: `npm run reveal-md`

You may also use `--theme puzzle` if you copy the theme directory into your project. More information (PDF and static site generation): https://github.com/webpro/reveal-md

The releases use Semantic Versioning. More information: http://semver.org/

## Styles
There are multiple styles that you can use:
* master01: dark blue
* master02: blue
* master03: light blue
* master04: turquoise
* master05: green

Just add this tag under your slides:
```
<!-- .slide: class="master01" -->
```

### Intro Slides
The intro class will add a numbered circle above the header.
```
## Second Topic
<!-- .slide: class="master04 intro" -->
```
![Puzzle ITC Revealjs Theme](demo2.png)

## Contributing
1. Run `npm install`
2. Run `npm run start`
3. Edit `puzzle.scss` in `css/theme/source`
4. Reload browser

## Full Installation (use this if you don't want to use markdown)
1. Download the latest version of reveal.js from https://github.com/hakimel/reveal.js/releases
2. Unzip and copy `puzzle.css` into `css/theme`
3. Update the included theme in `index.html`
4. Open `index.html` in a browser to view it
