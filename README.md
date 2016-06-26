# MathBox #

### Presentation-quality WebGL math graphing

![MathBox](http://acko.net/files/mathbox2/cover1.jpg)

MathBox is a library for rendering presentation-quality math diagrams in a browser using WebGL. Built on top of Three.js and ShaderGraph, it provides a clean API to visualize mathematical relationships and animate them declaratively.

MathBox is used through its JS-based DOM.

For background, see the [article series on Acko.net](http://acko.net/blog/mathbox2/).

**See `docs/` for TLDR and `examples/` for a start.**

Demos:

 * [Audio Visualizer](http://acko.net/files/mathbox2/iframe-readyornot.html)
 * [Cylindrical Stream](http://acko.net/files/mathbox2/iframe-cylindrical-stream.html)
 * [Data/Shape Mapping](http://acko.net/files/mathbox2/iframe-lineup.html)
 * [LaTeX/HTML/GL Labels](http://acko.net/files/mathbox2/iframe-labels.html)
 * [Quaternion Hypersphere](http://acko.net/files/mathbox2/iframe-quat.html)
 * [Render-to-Texture History](http://acko.net/files/mathbox2/iframe-rtt-history.html)
 * [Vertex Warping](http://acko.net/files/mathbox2/iframe-vertex.html)
 * [Volumetric Vectors](http://acko.net/files/mathbox2/iframe-volume.html)

Presentations:
 * [The Pixel Factory](http://acko.net/files/gltalks/pixelfactory/online.html#0)

*Note: this repo uses submodules, clone it with `--recursive` or do a `git submodule init`.*

***


## Download

* Release: [0.0.3 ZIP](http://acko.net/files/mathbox2/mathbox-0.0.3.zip)

or install via bower:

```bash
bower install mathbox
```


***
## Usage

Include the bundle:

```html
<script src="./mathbox-bundle.js"></script>
```

MathBox uses [threestrap](https://github.com/unconed/threestrap) to launch and shares all of its options.

```javascript
var mathbox = mathBox(options);
if (mathbox.fallback) throw "WebGL not supported";

var three = mathbox.three;
// three.renderer, three.scene, three.camera
```

On initialization, it returns a MathBox API object, wrapping the MathBox <root>. You can spawn new nodes:

```jsx
<cartesian range={[[-2, 2], [-1, 1], [-1, 1]]} scale={[2, 1, 1]}>
  <axis axis={1} />
  <axis axis={2} />
</cartesian>
```

via

```javascript
var view = mathbox
  .cartesian({
    range: [[-2, 2], [-1, 1], [-1, 1]],
    scale: [2, 1, 1],
  })
    .axis({
      axis: 1,
    })
    .axis({
      axis: 2,
    })
```

You can select objects using `.select()` and a CSS-like selector to get a jQuery-like selection:

```javascript
mathbox
  .select("cartesian > axis")
```

Use `.print()`, `.inspect()` and `.debug()` to show information about a selection.

***

## Docs & Help

See:

 * `docs/intro.md` for a tiny quickstart
 * `docs/primitives.md` for a full element reference
 * `docs/context.md` for advanced context usage.

Visit the [MathBox Google Group](https://groups.google.com/forum/#!forum/mathbox) or #mathbox on Freenode.

***

/src tree:

 * model/      - DOM tree + CSS selector handling
 * primitives/ - The DOM node types (the legos)
 * render/     - Smart proxies for Three.js (the glue)
 * shaders/    - GLSL code
 * stage/      - API / controllers
 * util/       - It's inevitable

/vendor

 * [threestrap](https://github.com/unconed/threestrap) - Three.js bootstrapper
 * [shadergraph](https://github.com/unconed/shadergraph) - Functional GLSL linker

Uses `gulp` to build itself.

***

MathBox and ShaderGraph (c) Steven Wittens 2013-2015. MIT License.

Libraries and 3rd party shaders (c) their respective authors.
