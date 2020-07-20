# Class 26 Reading: Webpack

## Intro to Webpack:
Webpack was created when websites went from consisting of a small number of files (HTML, CSS, and a few JavaScript files) to a bunch of different frameworks and libraries. Code became more <b>modular</b> (AKA, more complex sites could be made by putting smaller chunks of code in their own individual files), which meant the number of files used in each website increased.

Package code could not be easily understood by browsers, so devs used polyfills to make their code interpretable by the browser.

Webpack goes through your packages and creates <b>DEPENDENCY GRAPHS,</b> whjich are the modules needed to make your webapp function as expected. The graph is then used to create a new package which consists of the bare minimum number of files, often just a single bundle.js file, which can be plugged into the HTML file easily. 

``` $ npm i webpack webpack-dev-server webpack-cli --save--dev ```

## Webpack Concepts:
### entry
- indicates which module webpack should use to begin making the dependency graph.
```
module.exports = {
  entry: './path/to/my/entry/file.js'
};
```
### output
- Tells webpack where to emit the bundles and how to name the files.
```
const path = require('path');

module.exports = {
  entry: './path/to/my/entry/file.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'my-first-webpack.bundle.js'
  }
};
```
### loaders 
Allow webpack to process files that are not JavaScript and JSON into valid modules.
```
const path = require('path');

module.exports = {
  output: {
    filename: 'my-first-webpack.bundle.js'
  },
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  }
};
```
### plugins
- plugins can be leveraged to perform a wider range of tasks.
```
const HtmlWebpackPlugin = require('html-webpack-plugin'); //installed via npm
const webpack = require('webpack'); //to access built-in plugins

module.exports = {
  module: {
    rules: [
      { test: /\.txt$/, use: 'raw-loader' }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({template: './src/index.html'})
  ]
};
```
### mode
- Can be set to development, production, or none (webpack has optmnizations that correspond to each environment )
```
module.exports = {
  mode: 'production'
};
```
### browser compatability
- webpack works with ES5-compliant (IE8 and below are not supported). It needs Promise for import() and require.ensure(). For older browsers, a polyfill is needed.
## react hello world:
```js
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```
## introducing JSX:
```js
const element = <h1>Hello, world!</h1>;
```
- Example of JSX element. 
```js
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```
```js
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}
```

