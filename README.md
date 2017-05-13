# DanStough.github.io

DanStough.github.io is a statically-generated blog site hosted through [Github pages](https://pages.github.com/) and built using [Gatsby](https://github.com/gatsbyjs/gatsby). This site is meant to be an low maintenance and informal place to share my thoughts and experience related to software development and electrical engineering. Visit it live at the custom domain [stough.codes](http://stough.codes) and checkout my blog post about getting up and running with Gatsby (TBD).

The current iteration of this site uses the simple and elegant [Lumen starter theme](https://github.com/wpioneer/gatsby-starter-lumen) developed by Alexander Shelepenok. 

## Development

Gatsby enforces a technology stack built on [Node.js](https://nodejs.org/en/), [React](https://facebook.github.io/react/) and [Webpack](https://webpack.js.org/). This creates a fast, single-page web app while using developer-friendly technologies.

Some prerequisites are required to hack on this project:
* A recent version of Node.js installed on your system.
* [Gatsby](https://github.com/gatsbyjs/gatsby) installed globally via NPM.

Also, [React dev tools for Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi) are highly recommended for debugging (other browsers are supported as well).

After cloning this project repository, install the project dependencies via npm:

```
npm install
```

Gatsby uses Webpack to setup a local development server that supports hot reloading file changes (though not necessarily file additions) to test the end product. To spin up a development server:

```
gatsby develop
```

The site will then be visible in a browser at localhost:8000. Once the server is up, any saved changes will automatically be reflected in the browser. Now you can go nuts with edits! Closing the server is as simple as hitting `Ctrl + 'C'`.

React components, which define the site formating and structure, can be found in the `components` directory.

Post can be created by adding a directory under `articles` with an inner index.md. Posts are written in Markdown, making new content easy to create and format. The URL slug and top-level article titles are all declared in the front-matter header of the Markdown file; see some of the other existing posts for references on the front-matter syntax.

Pages are created in a similar manner under the `pages` directory, but have to be manually linked to from other places on the site in order to be accessed.

## Build and Deployment

The source files, including the Markdown content, in the `develop` branch need to be built into typical browser resources (i.e. HTML and ES5 JavaScript) by Gatsby. To build the website for distribution, run:

```
npm run build
```

In addition to the functionality of Gatsby's CLI build command, this NPM script will copy over some of the Github-specific static resources, such as the `CNAME` file used to define the custom domain name of the site. The result is a newly-generated `public` folder that contains all of the files needed to serve the site statically. You can test that the build process produces the expected results by running the development server directly out of the build directory like so:

```
gatsby serve-build
```

The branching model for the project is such that only the development files live on the `develop` branch, and only the build results live on `master`. It works this way because User Github Pages can only be served out of `master`, and *any* file in `master` will be served. For this reason, the two branches should *NEVER* be merged. 

This project uses the [gh-pages](https://www.npmjs.com/package/gh-pages) npm module to automate release deployment. To purge any existing build artifacts and automatically build the site into the master branch, run the following:

```
npm run clean
npm run deploy
```

## :loudspeaker: Shout-outs!

Thanks to all the great open source software and free services that make building a fantastic, modern and professional website easy:

* [Gatsby](https://github.com/gatsbyjs/gatsby)
* [Lumen](https://github.com/wpioneer/gatsby-starter-lumen/blob/master/README.md)
* [gh-pages](https://www.npmjs.com/package/gh-pages)
* [Node.js](https://nodejs.org/en/)
* [React](https://facebook.github.io/react/) 
* [Webpack](https://webpack.js.org/)
* [realfavicongenerator.net](http://realfavicongenerator.net)
* [Inkscape](https://inkscape.org/en/)
* [Font Squirrel](https://www.fontsquirrel.com/)

## About
This project is licensed under the terms of the [MIT license](https://github.com/DanStough/DanStough.github.io/blob/develop/LICENSE).

Copyright (c) 2017 Daniel Stough