# Rendering

## Overview
    * server rendering or static rendering  > full rehydration approach

## Terminology

#### Rendering
    * Server Side Rendering
        * render to an HTML on server
    * Client Side Rendering
        * plain html + js
        * run js in borwser to manipulate DOM
    * Rehydration
        * “booting up” JavaScript views on the client such that they reuse the server-rendered HTML’s DOM tree and data.
    * Prerendering
        * running a client-side application at build time to capture its initial state as static HTML.

#### Performance
    * TTFB: Time to First Byte - seen as the time between clicking a link and the first bit of content coming in.
    * FP: First Paint - the first time any pixel gets becomes visible to the user.
    * FCP: First Contentful Paint - the time when requested content (article body, etc) becomes visible.
    * TTI: Time To Interactive - the time at which a page becomes interactive (events wired up, etc).

## Server Rendering
* Overview
    * send an intricate html page to browser
        * a lot of js has been embedded into html
    * send an small amount of js for additional interaction
    * user only wait for thid-party js to load
    * good for streaming document parsing
    * takes time to generate html page which results in bad TTFB

* Features
    * good
        * FP
        * FCP
        * TTI
    * bad
        * TTFB

## Static Rendering
* Overview
    * generate html on build time
    * generate multiple html pages for different path
        * bad: you have to predict every possible path
    * can be deployed to CDN server (edge caching)

* Features
    * good
        * FP
        * FCP
        * TTFB
            * no need to generate html on request
        * TTI
            * prerequisite: limit amount of js files

* Note
    * Static Rendering v.s Pre-rendering
        * static rendering
            * can be interactive without much js
        * pre-rendering
            * html + bootup js
                * only improve: FP, FC
            * example
                1. SR + bootup js
                2. Static Rendering partial html + bootup js

* downside
    * development mess
        * different pages for different urls

## Server Rendering v.s Static Rendering
* ssr
    * upside:
        * pull more customized data
            * personalize dashboard
    * downside: more complex to development
        * need to cache
            * html page
            * js component

## Best Implementation
* SSR relatively static page for landing page and CSR + prefetching for other interaction-heavy pages.



## Client Side Rendering
* Overview
    * minimal html + big amount of js
        * do data fetching, routing, templatinn on client side
    * need to keep number of js files low
        * bundle
    * implement [HTTP2 server push](https://www.smashingmagazine.com/2017/04/guide-http2-server-push/) + `<link rel=preload>`
    * implement [PRPL](https://web.dev/apply-instant-loading-with-prpl/)
        * push (preload)
            * critical javascript
            * Render the initial route as soon as possible (improv first paint)
                * async not importanat javascript
                * server side rendering
            * Pre-cache assets
                * service worker
            * lazy load

* downside
    * complex app (a lot of js)
        * solutions
            * lazy load js
            * code splitting
            * Application Shell Caching (service worker)

* Features
    * good
        * FP
        * FCP
        * TTFB
    * Bad
        * really bad TTI


## [Note](#note)
* static rendering
    * benefit
        * FP, FCP, TTFB, TTI
    * downside
        * you have to predict all routes
        * template, not customized
* Server Rendering
    * benefit
        * FP, FCP, TTI
    * downside
        * TTFB
        * complex to implement

* CSR
    * benefit
        * FP, FCP, TTFB
    * downside
        * TTI
        * need to implement several solutions to optimize

## Questions / To Read
* streaming document parsing
* [Application Shell Caching](https://developers.google.com/web/updates/2015/11/app-shell)
* progress to [hydration](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)

## Refs
* [rendering - google](https://developers.google.com/web/updates/2019/02/rendering-on-the-web)
* [netflix case](https://medium.com/dev-channel/a-netflix-web-performance-case-study-c0bcde26a9d9)
