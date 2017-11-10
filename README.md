# coldbox-elixir-postcss
[![npm Version](https://img.shields.io/npm/v/coldbox-elixir-postcss.svg)](https://www.npmjs.com/package/coldbox-elixir-postcss)
[![npm License](https://img.shields.io/npm/l/coldbox-elixir-postcss.svg)](https://www.npmjs.com/package/coldbox-elixir-postcss)

This ColdBox Elixir extension allows you easy to compile PostCSS.


## Installation

```bash
$ npm install coldbox-elixir-postcss --save-dev
```


## Usage

Require this extension at the top of your `gulpfile.js`:

```js
require( "coldbox-elixir-postcss" );
```

Then you have access to the `postcss` function inside ColdBox Elixir:

```js
elixir( function( mix ) {
    // app.css, *.css, **/*.css
    mix.postcss( "app.css" );
} );
```

#### Using PostCSS Plugins

```js
elixir(function(mix) {
    mix.postcss( "app.css", {
        plugins: [
            require( "postcss-nested" )
        ]
    } );
} );
```

#### Using Other Parser

You can set the [options](https://github.com/postcss/postcss#options) using other parsers like `scss`, `sugarss` etc.

```js
elixir( function( mix ) {
    mix.postcss( "app.css", {
        options: {
            parser: require( "postcss-scss" )
        }
    } );
} );
```

Use `parser` and `plugins`.
```js
elixir( function( mix ) {
    mix.postcss( "app.css", {
        options: {
            parser: require("sugarss")
        },
        plugins: [
            require("postcss-nested")
        ],
    } );
} );
```


## Options

This extension accept two parameters:

* An string of files.
* An object of options.

Common options:

* `options`: See [postcss common options](https://github.com/postcss/postcss#options).
* `output`: destination"s path
* `plugins`: postcss"s plugins.
* `srcPath`: source's directory.
* `sourcemaps`: enable source map.
* `watchs`: additional watch directories.

#### Default Value
```js
{
    options    : {},
    output     : "public/css",
    plugins    : [],
    srcPath    : "resources/assets/postcss/",
    sourcemaps : true, // default value is the same as `elixir.config.sourcemaps`
    watchs     : [],
}
```
