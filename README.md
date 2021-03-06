# dts2as

A command line utility that converts TypeScript definitions (d.ts files) to ActionScript classes and interfaces and generates a SWC file. Use these SWCs with Apache FlexJS for strict compile-time type checking, as if the JavaScript library were written in ActionScript. Add the SWCs to IDEs, like Flash Builder and IntelliJ IDEA, and you'll get helpful code suggestions as you type.

## Installation

Requires [Node.js](https://nodejs.org/).

```
npm install -g dts2as
```

## Usage

```
dts2as hello.d.ts
dts2as file1.d.ts file2.d.ts
dts2as --outSWC hello.swc hello.d.ts
dts2as --outDir ./as3-files file.d.ts
dts2as --exclude com.example.SomeType file.d.ts
```

The following arguments are available:

* `-outSWC FILE`

	Generate a compiled SWC file. Requires either `FLEX_HOME` environment variable or `--flexHome` option.

* `-outDir DIRECTORY`

	Generate ActionScript files in a specific output directory. Defaults to `./dts2as_generated`.

* `--flexHome DIRECTORY`

	Specify the directory where Apache FlexJS is located. Defaults to `FLEX_HOME` environment variable, if available.

* `-e SYMBOL` or `--exclude SYMBOL`

	Specify the fully-qualified name of a symbol to exclude when emitting ActionScript.

* `-i SYMBOL` or `--include SYMBOL`

	Specify the fully-qualified name of a symbol to include when emitting ActionScript. Excludes all other symbols.

* `-t VERSION` or `--target VERSION`

	Specify ECMAScript target version for the TypeScript standard library: 'ES3', 'ES5' (default), or 'ES6'

* `-v` or `--version`

	Print the version of `dts2as`.

## Compiling with Apache FlexJS

To use the generated SWC file with Apache FlexJS, append it to the external library path:

```
asjsc --external-library-path+=generated.swc src/MyProject.as
```

For more details, please read the following tutorial:

[Introduction to `dts2as`: Using TypeScript definitions with ActionScript](http://nextgenactionscript.com/tutorials/dts2as-typescript-definitions-with-actionscript/)

## Support this project

Want to see more ActionScript transpiler tools and utilities like `dts2as`? How about in-depth articles and step-by-step video tutorials that teach you how to use ActionScript with libraries like jQuery, CreateJS, and Pixi.js? Please [become a patron](http://patreon.com/josht) and support the next generation of ActionScript development on the web -- without a plugin!

[NextGen ActionScript by Josh Tynjala on Patreon](http://patreon.com/josht)

Special thanks to the following sponsors for their generous support:

* [YETi CGI](http://yeticgi.com/)