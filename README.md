# Custom Component Template

## Getting Started

- run `npm install`
- choose a name for your component (e.g. my-name)
- run `npm run init -- --c=my-name`
- code away

## Basics

This repository acts as a template for creating new components for Hydrogren. Components are referred to throughout the repo as "component-[NAME]".

Important files to pay attention to:
- `dev/markup/h2-component-[NAME].html` (the file where your reference markup for the component will exist)
- `dev/scripts/h2-component-[NAME].js` (the file where your component scripts will go; you can use Cash functions here)
- `dev/styles/_component-[NAME].scss` (where your component's styles exist, all of which should be in mixins that are called by the following two files)
  - `dev/styles/h2-system-component-[NAME].scss` (the file that generates the styles needed by Hydrogen as a system)
  - `dev/styles/h2-version-component-[NAME].scss` (thie file that generates the unique standalone component code for this version of your component)
- `tests/index.html` (the file that is loaded when `npm run dev` is run; put markup in here to test your component)
- `npm.js` (the default JS file loaded for the package)
- `package.json` (the details of the npm package for your component)
- `README.md` (this file, please edit it to ensure other people can work with your component locally)

# Hydrogen: $COMP

Hydrogen's components are built using [Gulp](https://gulpjs.com/), [Sass](https://sass-lang.com), [Autoprefixer](https://github.com/postcss/autoprefixer), and [CSSnano](https://cssnano.co/).

Hydrogen components require [Cash](https://kenwheeler.github.io/cash/) to work properly. Cash is a lightweight jQuery alternative and will eventually be phased out of Hydrogen in favour of vanilla JavaScript.

This component module contains the following in the `dist` folder:
- the component's code that is imported by @hydrogen-design-system/system
- a versioned, isolated copy of the component that can be used independently of the system, either imported by a Sass project, or pulled as compiled CSS

This component currently supports the following markup and/or frameworks:
- raw HTML

* Please ensure that work on this component updates all supported markup where possible.

## Contributing

The core code for this component can be found in:
- dev/markup/
- dev/scripts/
- dev/styles/_component-$COMP.scss

You will need:
- [Node](https://nodejs.org/en/)

To contribute:
- `git clone` this repository
- `npm install`
- `npm run dev`

### Important Commands
- `npm install`
  - installs all development dependencies
- `npm run dev`
  - builds the versioned instance of the component and opens the test file in your browser with browser-sync running so that you can moderate your changes
- `npm run build`
  - runs the build command to process all files for production
  - this will automatically build the system and instanced versions of the component
- `npm publish`
  - builds the component
  - publishes it to the public package repository