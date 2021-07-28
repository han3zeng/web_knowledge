* Entry
    * webpack entry point
    * follow through to create graph dependenct
* Output
    * where to ouput bundle and name it
* Loaders
    * in default, webpack only recognize json file
    * loaders allow webpack to process other types of files and convert thme into valid modules
        * css, font, image, video, json, etc.
    * two properties
        * test: process what kind of files
        * use: use which loader
* Plugins
    * do wide range of tasks
        * bundle optimization
        * aseet management
        * injection of environment variables
* Mode
    * production
        * enable webpack build-in optimizations
* Browser Compatibility
    * to support older browser, you need to load a [polyfill](https://webpack.js.org/guides/shimming/)

## refs
* [webpack official](https://webpack.js.org/concepts)
