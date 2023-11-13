# Puzzle ITC Revealjs Theme

[![Puzzle ITC Revealjs Theme](imgs/demo-cover.png)](https://puzzle.github.io/pitc-revealjs-theme/demo)

Revealjs Dokumentation: https://github.com/hakimel/reveal.js


## Requirements
NPM must be installed. Instructions for Ubuntu are [here](https://github.com/nodesource/distributions#installation-instructions).


## Usage with NPM (recommended)

1. Copy the files in `example` to your repository.
2. Install the dependencies with `npm install`
3. Open the presentation with `npm run start`

**Note:** If you have multiple presentations, replace `slides.md` in `package.json` with a dot (`.`).


### Print

1. Start your presentation with `npm run start`
2. Open another terminal and run `npm run print`
3. If everything worked, your slides will be in `slides.pdf`

### Static generation

For offline presentations and if you want to be very sure nothing changes, use `npm run static`. Make sure to test your presentation! Sometimes image paths are not correct or the images must be manually copied to `_static/_assets`.


## Usage with Docker

```
docker run --rm -p 1948:1948 -v $(pwd):/slides webpronl/reveal-md:latest --watch --theme https://puzzle.github.io/pitc-revealjs-theme/2/puzzle.css /slides
```

### Print

1. Start your presentation in another terminal
2. Run the following command:
```
docker run --rm -t --net=host -v $(pwd):/slides astefanutti/decktape http://localhost:1948/slides.md slides.pdf
```

## Global Installation
1. Install reveal-md: `sudo npm install -g reveal-md`
2. Open the presentation:

    ```reveal-md demo.md --watch --theme https://puzzle.github.io/pitc-revealjs-theme/2/puzzle.css```

Optional: Add an alias in your `.bashrc`:
```
alias reveal-md='reveal-md --watch --theme https://puzzle.github.io/pitc-revealjs-theme/2/puzzle.css'
```


## Versions

The following versions are available:
- `latest`
- Git sha (e.g. `07ff323`)
- Major version (e.g. `2`)
- Minor version (e.g. `2.0`)
- Patch version (e.g. `2.0.0`)

The major version is automatically updated, when there are compatible new features. The minor version is only updated when there are new patches.

See the [Github Tags](https://github.com/puzzle/pitc-revealjs-theme/tags) for available releases.

You can then use the version within the URL:
```
https://puzzle.github.io/pitc-revealjs-theme/${VERSION}/puzzle.css"
```

Use the version `1.0.2` for the old theme.

The releases use Semantic Versioning. More information: http://semver.org/


## Layouts
See https://puzzle.github.io/pitc-revealjs-theme/demo for a demo. Every slide has a vertical slide below, that describes its usage.


## Options

There are multiple options to configure a single slide. In the official documentation these are HTML attributes on the section `<section data-XX>`. You may add these in the slide comment:
```
<!-- .slide: data-background-color="aquamarine" -->
```

- [Backgrounds](https://revealjs.com/backgrounds/)
- [Math](https://revealjs.com/math/#markdown)
- [Layout](https://revealjs.com/layout/)
- [Slide Visibility](https://revealjs.com/slide-visibility/)
- [Transitions](https://revealjs.com/transitions/)
- [Advanced: Auto Animate](https://revealjs.com/auto-animate/)
- [Speaker View](https://revealjs.com/speaker-view/)


You may link to a specific slide:
```
<!-- .slide: id="test" -->
# Test

---
# Another slide
[Link](#test)
```

Some features like [Media](https://revealjs.com/media/) also require HTML instead of Markdown:

```
<video data-autoplay src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4"></video>
```

## Fragments
[Fragments](https://revealjs.com/fragments/) can be used in Markdown with the following:
```
- Item 1 <!-- .element: class="fragment" data-fragment-index="2" -->
- Item 2 <!-- .element: class="fragment" data-fragment-index="1" -->
```

## Code Highlighting

Specific parts of code can be highlighted:
````
```js [1-2|3|4]
    let a = 1;
    let b = 2;
    let c = x => 1 + 2 + x;
    c(3);
```
````
See the [official documentation](https://revealjs.com/code/#line-numbers-%26-highlights) for more information.

## Custom CSS

To override CSS you may add `--css custom.css` to the `reveal-md` command. This is usally located in `package.json`.


## Contributing
1. Run `npm install`
2. Run `npm run start`
3. Edit `puzzle.scss` in `css/theme/source`
4. Reload browser

To release a new version:
```
git tag 1.2.3
git push --tags
```

Always use the format `major.minor.patch` and follow Semantic Versioning. More information: http://semver.org/
