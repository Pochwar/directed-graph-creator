# directed-graph-creator

## Info

This package is a fork of https://github.com/metacademy/directed-graph-creator made for use with NPM

## About
Interactive tool for creating directed graphs, created using d3.js.

Demo: http://bl.ocks.org/cjrd/6863459

<p align="center">
<img src="http://obphio.us/media/images/digraph-creator.png" alt="Metacademy Logo" height="350px"/>
</p>

Operations:

* drag/scroll to translate/zoom the graph
* shift-click on graph to create a node
* shift-click on a node and then drag to another node to connect them with a directed edge
* shift-click on a node to change its title
* click on node or edge and press backspace/delete to delete

## Installation

- run `npm install https://github.com/Pochwar/directed-graph-creator.git -S`
- create `./webpack.mix.js` and copy the following lines :
```
var mix = require('laravel-mix');
mix.disableSuccessNotifications()
  .copy('node_modules/directed-graph-creator/resources/css/graph-creator.css', 'public/css')
  .copy('node_modules/directed-graph-creator/resources/img/download-icon.png', 'public/img')
  .copy('node_modules/directed-graph-creator/resources/img/thumbnail.png', 'public/img')
  .copy('node_modules/directed-graph-creator/resources/img/trash-icon.png', 'public/img')
  .copy('node_modules/directed-graph-creator/resources/img/upload-icon.png', 'public/img')
  .combine([
    'node_modules/directed-graph-creator/node_modules/d3/d3.js',
    'node_modules/directed-graph-creator/node_modules/file-saver/FileSaver.js',
    'node_modules/directed-graph-creator/resources/js/graph-creator.js'
  ], 'public/js/graph-creator.js')
```

- Add the following lines to your `package.json` scripts lines :
```
"fdev": "NODE_ENV=development webpack --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
"fwatch": "NODE_ENV=development webpack --watch --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
"fhot": "NODE_ENV=development webpack-dev-server --inline --hot --config=node_modules/laravel-mix/setup/webpack.config.js",
"fproduction": "NODE_ENV=production webpack --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js"
```

- Compile files : `npm run fdev`

- Copy the following code in your HTML file :
```
<div id="graph">
    <div id="toolbox">
      <input type="file" id="hidden-file-upload"><input id="upload-input" type="image" title="upload graph" src="img/upload-icon.png" alt="upload graph"> <input type="image" id="download-input" title="download graph" src="img/download-icon.png" alt="download graph"> <input type="image" id="delete-graph" title="delete graph" src="img/trash-icon.png" alt="delete graph">
    </div>
</div>

<script src="js/graph-creator.js"></script>
```
- dont forget to declare `<meta charset="UTF-8">` in the `<head>`  of your document

## License
MIT/X







