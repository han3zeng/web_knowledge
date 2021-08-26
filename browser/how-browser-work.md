## Network
1. DNS lookup
1. three way handshake (TCP handshake)
2. TLS negotiation (SSL) (SSL handshake)
3. TCP slow start - 14 kb rule

## In Browser Parsing

1. Building DOM Tree (parse)
    * request and download css do not block the html parsing
    * requeset adn downlaod script block the html parsing
2. Building the CSSOM
    * ia map of all CSS selectors and relevant properties for each selector in the form of a tree, with a root node, sibling, descendant, child, and other relationship.
        * the structure is just like DOM Tree but without <meta>, <script>, <title>

    * **using specificity rules** will override **user agent stylesheet**(browser preset style which can cause cross browser issue)
        * you mayu need normalize.css to solve such problem
    * note
        * really fast
        * create style
        * at the same time, JavaScript files are downloading (by preload scanner)

  * preload scanner
      * while the main thread is parsing, the scanner find out what resources should be downloaded. So the browser can download images, styles, javascripts during the parsing
      * script should add async or defer so that it will not block the main thread from parsing
      * fetching css file, which will not block the html parsing but it will block the javascript


## Renderting
* style, layout, paint, composite

#### style
* combine DOM + CSSOM tree to get a render tree
    * in render tree
        * visibiility: hidden, opacity: 0
    * not in render tree
        * display none
        * width, height: 0
* redner tree only determine what node should be displayed


#### Layout
* compute dimension and location of each node in render treer based on different viewport
* steps
    1. layout
        * frist render on the browser without knowing image size
    2. reflow
        * recalculate location once the image size is known

#### Paint
* raterization (layout to pixels)
* draw differnt specific elements in to different layers
    * help to rerender, animate quickly

#### composite
* composite all layers
    *  composite process make sure that all layers are drawn to the screen in the right order and the content is rendered correctly.

* performance example
    * reflow -> repaint -> recomposite
        * with predfiend size image
            * only modify the layer
            * repaint and recomposite the necessary layer
        * with undefined size image
            * raterizae again to create multiple layers
            * relocation (lauouy) -> repaint -> recomposite


## Interactivity
* browser render the page, but the main thread is running some code from onload() in some javascripts. So user can not intercate with the page (perfomacne issue)

* https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/#The_main_flow
* https://developer.mozilla.org/en-US/docs/Web/Performance/How_browsers_work
* https://medium.com/jspoint/how-the-browser-renders-a-web-page-dom-cssom-and-rendering-df10531c9969
    * i should check this out again
