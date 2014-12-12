**Warning! Experimental status, work in progress**

#flowscript

**flowscript** is a reactive dataflow programming language for scientist, engineers and hobbyists.

A program is a simple JSON file with an array of nodes.
A node is an object that reference a node.js function, where the parameters are the inputs and the returns are the output.
Each node is executed in sequence according to the connection inter the input and the output nodes.

This language will have sense when has a visual IDE, that is coming soon in a separate package.
In any case, flowscript is IDE agnostic.

#Installation
```sh
$ npm install flowscript -g
```

##Usage

```sh
$ # compile
$ flowscript myprogram.json > myprogram.js
$ # execute
$ node myprogram.js val1 val2
```

```node
var flow = require('flowscript'),
	fs = require('fs')

var program = flow.compile(fs.readSync('myprogram.json'));

program
	.exec(0,0,0,1)
	.spread(function (total, n) {
	
})

```