### MathBox Changelog

0.0.4

 * New <readback /> sink that exposes internal readback functionality.
 * Make <array />, <matrix />, <voxel /> and <text /> auto-detect `null` dimensions from `data` if given.
 * Fix <text /> not parsing >1 string from an array.
 * Fix public `channels` on <text /> being 4 instead of 1.
 * Removed unused font properties from <retext />.
 * Fix final/const props being overwritable on initial set.
 * Rename <text expand={n} /> to <text sdf={n} /> (signed distance field) to avoid confusion with <label expand={n} />
 * Change default <label /> color from black to gray to match other primitives.
 * Fix data array emitters for larger item sizes.
 * Add thunk lerper to animate data arrays on keyframe tracks.
 * Remove default zOrder on <axis /> and <grid />.
 * Clean slate NPM dependencies.
 * Fix `gulp-rename` compatibility.
 * Improved axis, grid, helix, lerp, label, strip examples.
 * Improved idiomatic time examples.
 * New color cube, vertex color, fragment color, tiles and ortho examples.
 * Document instanced traits (e.g. `divideX`) and non-standard defaults.
 * Support fragment passes on unshaded geometry.
 * Added `lineBias` prop to set Z-bias between surface/face and its wireframe.
 * Allow passing modified STPQ coordinates from <vertex /> to <fragment /> (see `fragmentcolor.html` example)

0.0.3

 * New `docs/intro.md`, add nullable examples to `docs/primitives.md`.
 * Add `sizes` binding to <point /> to change per-point size.
 * New <mask /> pass for custom transition effects, remove clip leftover.
 * Fix <clock> reporting incorrect real time and delta.
 * Fix <step /> counting repeated stops as skips.
 * Fix docs on <transition> `durationEnter`/`Exit`.
 * Fix <scale /> not tracking span changes.
 * Fix color [r, g, b] syntax parser.
 * Remove children in reverse order to avoid reindexing.
