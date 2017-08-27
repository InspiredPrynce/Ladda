# Ladda

Buttons with built-in loading indicators, effectively bridging the gap between action and feedback.

[Check out the demo page](http://lab.hakim.se/ladda/).

## Instructions

Release downloads and change history is available here <https://github.com/hakimel/Ladda/releases>.

The compiled files for the project that you should be using are available in the **/dist** directory. You will need to include both the **ladda.min.js** and **spin.min.js** files as well as ONE of the two style sheets. If you want the button styles used in the [Ladda example page](http://lab.hakim.se/ladda) use the **ladda.min.css** file, if you want to have the functional buttons without the visual style (colors, padding etc) use the **ladda-themeless.min.css** file.

#### HTML

Ladda buttons must be given the class `ladda-button` and the button label needs to have the `ladda-label` class. The `ladda-label` will be automatically created if it does not exist in the DOM. Below is an example of a button which will use the expand-right animation style.

```html
<button class="ladda-button" data-style="expand-right"><span class="ladda-label">Submit</span></button>
```

Buttons accept the following attributes:
- **data-style**: one of the button styles, full list in [demo](http://lab.hakim.se/ladda/) *[required]*
- **data-color**: green/red/blue/purple/mint
- **data-size**: xs/s/l/xl, defaults to medium
- **data-spinner-size**: 40, pixel dimensions of spinner, defaults to dynamic size based on the button height
- **data-spinner-color**: A hex code or any [named CSS color](http://css-tricks.com/snippets/css/named-colors-and-hex-equivalents/).
- **data-spinner-lines**: 12, the number of lines the for the spinner, defaults to 12

#### JavaScript

If you will be using the loading animation for a form that is submitted to the server (always resulting in a page reload) you can use the `bind()` method:

```javascript
// Automatically trigger the loading animation on click
Ladda.bind( 'button[type=submit]' );

// Same as the above but automatically stops after two seconds
Ladda.bind( 'button[type=submit]', { timeout: 2000 } );
```

If you want JavaScript control over your buttons you can use the following approach:

```javascript
// Create a new instance of ladda for the specified button
var l = Ladda.create( document.querySelector( '.my-button' ) );

// Start loading
l.start();

// Will display a progress bar for 50% of the button width
l.setProgress( 0.5 );

// Stop loading
l.stop();

// Toggle between loading/not loading states
l.toggle();

// Check the current state
l.isLoading();

// Delete the button's ladda instance
l.remove();
```

All loading animations on the page can be stopped by using:

```javascript
Ladda.stopAll();
```

## Module

You can `npm install ladda`. The spinner and Ladda can be loaded as a module using AMD or CommonJS.

```javascript
// Using RequireJS
define(['ladda'], function(Ladda) {
	// Make Buttons Here
});
```

Or in CommonJS, you will:

```javascript
var ladda = require('ladda');
```

## Browser support

The project is tested in Chrome, Firefox, and Edge. It Should Work™ in the current stable releases of Chrome, Firefox, Edge, and Safari, as well as IE9 and up.

## Changelog

<https://github.com/hakimel/Ladda/releases>

## License

MIT
