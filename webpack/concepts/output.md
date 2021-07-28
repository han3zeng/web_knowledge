## Overview
* unique output config
* multiple entries: use substitution to set unique name for each entry files in output directory


## Public Path v.s Path
* output.path
    * the place that webapck output all bundles to
    * ex: `output.path='dist'`

* output.publicPath
    * the path that webpack will use as reference to fetch data from output.Path
    * you can use it in html
        * ex
            * output.publicPath = '/assets'
            * <img src="han3zeng-og.jpg" />
                * re-writes: /assets/han3zeng-og.jpg
                    * accessed by url: /webroot/assets/han3zeng-og.jpg
                        * fetch from: `/project-directory/dist/han3zeng-og.jpg`



## Refs
* [output - concept - webpack](https://webpack.js.org/concepts/output/)
* [output.path v.s output.publicPath - stackoverflow](https://stackoverflow.com/questions/28846814/what-does-publicpath-in-webpack-do)
* [public path - guide - webpack](https://webpack.js.org/guides/public-path/)
