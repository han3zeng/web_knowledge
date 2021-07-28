## code-splitting
* multiple bundles
* lazy-load


## Webapck code-splitting
* preload
    * load the resources as early as possible
    * the resources that is needed in this navigation
    * do not block page layout
    * priority: medium
    * benefits
        * improve loading speed
            * load necessary assets first
                * A preloaded chunk starts loading in parallel to the parent chunk
                    * no need another request
        * preload css
            * ciritcal css
                * above the fold
        * preload resources (fontFamilt)
            * prevent flash of unstyled text
        * preload javascript
            * split javascript to seveal chunks
                * preload necessary chunks first
            * improve tiem to interactive

* prefetch
    * the resouces that is need in future navigation
    * load the resource in browser idle mode
        * use case
            * say, prefetch modal, so if user click on button and want to open modal, he/her dosen't have to wait
    * cost additional bandwidth
        * if use do not navigate the item
    * tips
        * priortize your prefetch
## Notes
* in webpack: prefetch is more common
* in html page: preload is more common


## code splitting and SSR
* overview
    * they are independent to each other
* code splitting
    * improve loading time
    * decrease initial loadding size
    * improve first contentful paint
* SSR
    * SEO
    * simple route code split
    * faster initial render
    * critical css (inline css)
## Refs
* [prefetch v.s preload - webpack](https://medium.com/webpack/link-rel-prefetch-preload-in-webpack-51a52358f84c)
* [preload critical assets - web.dev](https://web.dev/preload-critical-assets/
* [ssr + code spliting v.s code splitting](https://stackoverflow.com/questions/53071053/the-pros-and-const-of-react-ssr-with-code-splitting-and-now-react-lazyf)
