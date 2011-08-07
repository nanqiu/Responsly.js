# Responsly.js

## WHAT
Dead simple responsive widgets, written using CSS3 transformations and available as a jQuery Plugin.
Currently a sideshow and accordion are available, more to come!


## WHY
Responsive designs are cool! Not only do they allow you to reach mobile and tablet users with minimal effort, they also make your context scale up for desktop users with larger screens.

Unfortunately it means in general you can't use fixed sizes throughout your CSS. While this may not be a problem for new sites, a lot of existing widgets are hard-coded to various sizes.

I had this problem when building my [blog](http://dharmeshmalam.com), and at our startup [Quillu](http://quillu.com), so I developed a slideshow and accordion using various techniques to ensure they scale with their content and well as their containing div. This comes down to ensuring that width or height are never hard coded in the CSS. Also extensive use of CSS3, particularly the transitions ensures rich UI that works great in modern browsers, with graceful degradation for IE.

We though the work could be useful for others, so it was extracted into a library for reuse.

## DEMO

Check out the [demo](http://dmmalam.github.com/Responsly.js/)


## FEATURES
* Works from large monitors to laptops, to tablets to mobiles.
* Pure CSS styling
* CSS3 based transitions (hardware accelerated where possible).
* Animations work on all modern browsers including mobile, (IE degrades gracefully by losing transitions).
* Minimal dependence on jQuery for convenience ( can substitute Zepto, or pure JavaScript).
* Simple lightweight design, adds little to your download size
* Compartmentalized, so use only what you want
* Best used with a responsive CSS framework like 1140px or 320plus
* Can be heavily customized by editing CSS

## HOW
* Download / Clone files
* Add references to CSS / JS
* Add boilerplate placeholder HTML
* Use jQuery to attach widgets.
* See demo.html for examples.

## Library
Currently there are two widgets

### Slidy
A responsive CSS based animating sideshow with many options

* Options
    * Show / hide buttons
    * Use keyboard navigation
    * Auto start slideshow, set intervals
    * Can use throttling with [jQuery throttle plugin](http://benalman.com/projects/jquery-throttle-debounce-plugin/)

* Setup
    1. Add references, make sure jQuery is available

        ```html
            <link rel="stylesheet" href="slidy.css">
            <script src="slidy.js"></script>
        ```
    2. Add boilerplate HTML to wherever your want the slideshow. This is usually some responsive container

        ```html
        <div id="slidyBanner" class="slidyContainer" title="Your tooltip text">
                <div class="slidySlides">

                    <!-- Each slide is wrapped in figure section -->

                    <!-- Slide 1 -->
                    <!-- add the 'slidyCurrent' class to which slide you want as default -->
                    <figure class="slidyCurrent">
                        <!-- Your context goes here -->
                        <img  alt="Uyuni, Bolivia" src="img/banner/16 Uyuni Salt Flats - 61 - Banner.jpg">
                        <!-- Use the figcaption element to add captions -->
                        <figcaption>An Image</figcaption>
                    </figure>

                    <!-- Slide 2 -->
                    <figure>
                        <img  alt="Shanghai, China"  src="img/banner/2 Shanghai - 38 - Banner.jpg">
                        <figcaption>Another image</figcaption>
                    </figure>

                    <!-- Slide 3 -->
                    <figure>
                        <p> I am some text</p>
                        <p> Your not limited to images, you can have what ever you want </p>
                        <figcaption>Text</figcaption>
                    </figure>

                    <!-- Add more slides as necessary -->

                </div>
        </div>
        ```
    3. Wire up with options

        ```javascript
            <script>
            $('.slidyContainer').slidy({
                // Options go here, see slidy.js
                // These the defaults so don't only need to be specified if they are changed

                throttle: false, // Set to true, and include jQuery throttle plugin (http://benalman.com/projects/jquery-throttle-debounce-plugin/)
                throttleTime: 500, // number of ms to wait for throttling
                showArrows: true, // Show arrows for next/prev image
                movePrev: 'movePrev', // Div id to use for previous button
                moveNext: 'moveNext', // Div id to use for next button
                useKeybord: true, // use keys defined below to expand / collapse sections
                auto: false,       // Start slideshow automatically
                interval: 6000,     // Time between each slide
                initialInterval: 10000  // Initial interval when page loads

            });

        </script>
        ```
### Accordy
A responsive CSS based animating accordion.

* Options
    * Use keyboard navigation
    * Can use throttling with [jQuery throttle plugin](http://benalman.com/projects/jquery-throttle-debounce-plugin/)

* Setup
    1. Add references, make sure jQuery is available

        ```html
            <link rel="stylesheet" href="accordly.css">
            <script src="accordly.js"></script>
        ```
    2. Add boilerplate HTML to wherever your want the accordion. This is usually some responsive container

        ```html
            <div class="accordion">
                <!-- Section 1 -->
                <section>
                    <hgroup>
                        <h4>Section 1 title</h4>
                    </hgroup>
                    <article>
                        <h2> Put your content here </h2>
                    </article>
                </section>

                <!-- Section 2 -->
                <section>
                    <hgroup>
                        <h4>Section 2 title</h4>
                    </hgroup>
                    <article>
                        <h2> This is more context and can contain anything</h2>
                    </article>
                </section>

                <!-- Add more sections as needed -->

            </div>
        ```
    3. Wire up with options

        ```javascript
                $('.accordion').accordy({
                // Options go here, see slidy.js
                // These the defaults so don't only need to be specified if they are changed

                throttle: false, // Set to true, and include jQuery throttle plugin (http://benalman.com/projects/jquery-throttle-debounce-plugin/)
                throttleTime: 500, // number of ms to wait for throttling
                useKeybord: true, // use keys defined below to expand / collapse sections
                keyPressUp: 75, //K
                keyPressDown: 74 //J
            });

        ```


## CONTRIBUTE
We actively encourage additional widgets or improvements or features.
As usual fork, and submit pull requests

## TODO
* Add mobile touch events
* Find a workaround for webkit/mozilla bug, that stops transition with height is set to 100%

## Contact<
Dharmesh Malam (dmmalam@gmail.com)

## LICENSE
Copyright © 2011 by D MALAM

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

