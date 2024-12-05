---
layout: spell
date: 04-12-2024
---

## Base setup: node environment and webpack environment

- `npm` is a package manager for node javascript environmnent.
- `package.json` is the config file is associated with npm.
- `package-lock.json` is the dependency graph to support the requirements listed in the package.json file.

<br>

- `webpack` is a package that bundles front end web files together.  Multiple javascript files which are separate modules, can be bundled together.
- `webpack.config.js` is the config file associated with webpack.

<br>

```shell
# Initialise environment for packages to be managed.
mkdir myProject &&
cd myProject &&
npm init -y
```

```shell
# Locally install packages, install webpack and related tools
# -D flag equivalent to --save-dev
# -D registers the dependency as a development environment dependency
npm install -D webpack webpack-cli
```

```shell
mkdir src &&
touch src/index.js &&
touch src/module1.js
```

```js
// module1.js
export const x = "Hello, world!";
```

```js
// index.js
import { x } from "./module1.js";

console.log(x);
```

```js
// webpack.config.js file in root directory

// use path library
const path = require("path");

// specifications, self-explanatory
module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist"),
    // clears out obsolete files in distribution folder
    clean: true,
  },
};
```

```shell
# equivalent to `npm exec webpack`
# uses the webpack.config.js file as input and creates the outputs
npx webpack
```

<br>

## Web Setup

```shell
# to bundle html files
npm install -D html-webpack-plugin

# to bundle css files
npm install -D style-loader css-loader

# to bundle images
npm install -D html-loader

# to automate bundling
npm install -D webpack-dev-server
```

<br>

bundling html files

```js
// webpack.config.js
// to manage html files
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist"),
    clean: true,
  },
  // plugins key contains a list of plugins
  // initialise a new HtmlWebpackPlugin object
  // pass lambda object with template key
  plugins: [
    new HtmlWebpackPlugin({
        template: "./src/template.html",
    }),
  ],
};
```

```html
<!-- ./src/template.html -->
<!-- note no javascript tags needed -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

```shell
# now outputs a dist/index.html file
npm exec webpack
```

<br>

bundling css files

```js
// webpack.config.js
// to manage css files
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist"),
    clean: true,
  },
  plugins: [
    new HtmlWebpackPlugin({
        template: "./src/template.html",
    }),
  ],
  // module key has a rules key
  // rules contains a list of lambda objects
  // this lambda object has the test key and the use key
  module: {
    rules: [
        {
            test: /\.css$/i,
            // style-loader is run after css-loader
            // is the reverse order to do with array popping?
            use: ["style-loader", "css-loader"],
        },
    ],
  },
};
```

```css
/* style.css */
body {
    background-color: black;
}
```

```js
// index.js
// import listing here determines order stylesheets get added
// side effect import of style.css
import "./style.css";
import { x } from "./module1.js";

console.log(x);
```

<br>

bundling image files

```js
// webpack.config.js
// to manage image files
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist"),
    clean: true,
  },
  plugins: [
    new HtmlWebpackPlugin({
        template: "./src/template.html",
    }),
  ],
  module: {
    rules: [
        {
            // handles images in css files loaded in url()
            test: /\.css$/i,
            use: ["style-loader", "css-loader"],
        },
        {
            // handles parsing of file paths so that images can be loaded in the img[src] attribute
            // loader key, specific to the html-loader module
            test: /\.html$/i,
            loader: "html-loader",
        },
        {
            // handles images in javascript files in img.src
            // type key, specific to html-loader module
            test: /\.(png|svg|jpg|jpeg|gif)$/i,
            type: "asset/resource",
        },
    ],
  },
};
```

```js
// index.js
import wyethImage from "./wyethknightsofbaja.jpg";
import "./style.css";
import { x } from "./module1.js";

const image = document.createElement('img');
img.src = wyethImage;

document.body.appendChild(image);

console.log(x);
```

<br>

utilities

```js
// webpack.config.js
// add utilities
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    filename: "main.js",
    path: path.resolve(__dirname, "dist"),
    clean: true,
  },
  // source map decompiles the bundled code to help with debugging
  devtool: "eval-source-map",
  // development server automatically rebuilds javascript files,
  // for html files they need to be listed
  devServer: {
    watchFiles: ["./src/template.html",],
  }
  plugins: [
    new HtmlWebpackPlugin({
        template: "./src/template.html",
    }),
  ],
  module: {
    rules: [
        {
            test: /\.css$/i,
            use: ["style-loader", "css-loader"],
        },
        {
            test: /\.html$/i,
            loader: "html-loader",
        },
        {
            test: /\.(png|svg|jpg|jpeg|gif)$/i,
            type: "asset/resource",
        },
    ],
  },
};
```

```shell
npm exec webpack server
```