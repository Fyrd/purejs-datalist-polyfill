purejs-datalist-polyfill
========================

A pure JS (no jQuery required) implementation of the HTML5 datalist element

After being unable to find a polyfill for the [datalist element](http://www.w3.org/TR/html-markup/datalist.html) that both works in IE8+ and does not have dependencies, I decided to write my own. The implementation is largely inspired by the [Relevant Dropdown](https://github.com/CSS-Tricks/Relevant-Dropdowns) jQuery polyfill by [Chris Coyier](https://github.com/chriscoyier), with a few additions.

## Usage ##
Simply include the minified script and CSS file and make sure the script runs after the DOM's ready by adding it to the end of your HTML's body, or to include conditionally when support is missing use something like [yepnope.js](http://yepnopejs.com).

In order for the polyfill to work in IE8 and IE9 you'll also need to make sure your markup includes conditional comments at the start and end of the list of options like this:

    <datalist id="YOUR-LIST-ID">
        <!--[if lte IE 9]><select data-datalist="YOUR-LIST-ID"><![endif]-->
        <option value="item1"> 
        <option value="item2"> 
        <!--[if lte IE 9]></select><![endif]-->
    </data

Make sure the string "YOUR-LIST-ID" is replaced in both cases with the same id of your datalist.

See also the [http://a.deveria.com/tests/datalist/](sample demo) for an example of usage.

## Features ##
- No jQuery or any other library required
- Support for selection by keyboard
- Triggers 'change' event on input field when option from list is selected
- Easily customized CSS class names and styles
- Tested on IE8, IE9, Safari 6, iOS Safari 6, Android browser 4.x, and should work on any most older browsers [without support](http://caniuse.com/#feat=datalist) too (excluding IE7 and older).
