# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

reveal.js is an open-source HTML presentation framework. The codebase is built using vanilla JavaScript (ES6+) with a modular architecture and uses Gulp for build automation.

## Commands

### Development
- `npm start` - Start development server with live reload (port 8000 by default)
- `gulp serve` - Alternative to npm start, supports custom port/host via `--port` and `--host` flags

### Building
- `npm run build` - Build all distribution files (JS bundles, CSS, and plugins)
- `gulp build` - Alternative to npm run build
- `gulp js` - Build only JavaScript bundles (UMD and ES module formats)
- `gulp css` - Build only CSS files (core and themes)
- `gulp plugins` - Build only plugin bundles

### Testing
- `npm test` - Run ESLint and QUnit tests
- `gulp test` - Alternative to npm test
- `gulp eslint` - Run linting only
- `gulp qunit` - Run QUnit tests only (uses Puppeteer to test in browser)

### Packaging
- `gulp package` - Create a zip file of the presentation with all necessary files

## Architecture

### Core Structure

The main reveal.js instance is defined in `js/reveal.js` and exported through `js/index.js`. The architecture uses a controller pattern where different aspects of the presentation are managed by separate controller modules:

**Controllers** (`js/controllers/`):
- `slidecontent.js` - Manages slide content loading/unloading and embedded media
- `slidenumber.js` - Handles slide numbering display
- `backgrounds.js` - Manages slide backgrounds and parallax effects
- `autoanimate.js` - Controls auto-animation between slides
- `scrollview.js` - Implements scroll-based presentation mode
- `printview.js` - Handles print/PDF layout
- `fragments.js` - Manages fragment stepping and visibility
- `overview.js` - Overview mode functionality
- `keyboard.js` - Keyboard navigation and shortcuts
- `location.js` - URL hash management and deep linking
- `controls.js` - Navigation control UI
- `progress.js` - Progress bar
- `pointer.js` - Pointer/laser functionality
- `plugins.js` - Plugin loading and management
- `touch.js` - Touch gesture handling
- `focus.js` - Focus management
- `notes.js` - Speaker notes functionality

Each controller is instantiated in `reveal.js` and receives a reference to the main Reveal instance.

### Plugin System

Built-in plugins are located in `plugin/` directory:
- `highlight/` - Syntax highlighting (uses highlight.js)
- `markdown/` - Markdown slide support (uses marked)
- `search/` - Presentation search functionality
- `notes/` - Speaker notes window
- `zoom/` - Zoom functionality
- `math/` - LaTeX math rendering

Each plugin is built as both UMD and ES module format by the `plugins` gulp task.

### Build System

Uses Gulp with Rollup for JavaScript bundling:
- **Two JavaScript bundles**: UMD bundle (`dist/reveal.js`) for broad browser support with Babel polyfills, and ES module bundle (`dist/reveal.esm.js`) targeting modern browsers only
- **Sass compilation**: Core styles and themes are compiled from `css/` directory using the Dart Sass implementation
- **Plugin bundling**: Each plugin gets both UMD and ESM versions
- Build cache is maintained between builds for faster incremental compilation

### Configuration System

Default configuration is defined in `js/config.js` and can be overridden:
1. During Reveal initialization via `Reveal.initialize(options)`
2. Through `Reveal.configure(options)` method
3. Via URL query parameters (see `Util.getQueryHash()`)

### View Modes

reveal.js supports three view modes:
- **Default slide mode**: Standard slide-by-slide navigation
- **Scroll view** (`config.view = 'scroll'`): Vertical scrolling presentation
- **Print view** (`config.view = 'print'`): PDF-optimized layout

The active view is controlled by the ScrollView and PrintView controllers.

### Slide Structure

Slides are represented as `<section>` elements:
- Horizontal slides: Direct children of `.slides` container
- Vertical slides: Nested `<section>` elements create vertical stacks
- Slide state is managed through CSS classes: `past`, `present`, `future`
- Background elements are created and managed by the Backgrounds controller

## Development Notes

- Minimum Node.js version: 18.0.0
- Browser targets are defined in `package.json` under `browserslist`: "> 2%, not dead"
- ESLint configuration is defined in `package.json` under `eslintConfig`
- The codebase uses ES6+ features (classes, arrow functions, async/await, etc.)
- HTML imports are transformed to strings during build via `babel-plugin-transform-html-import-to-string`
- Tests are written using QUnit and run in Puppeteer-controlled browser instances
- The development server uses `gulp-connect` with LiveReload
