# Javascript API for Board plugins

## A plugin's structure

Each plugin consists of at least one ES6 module which is imported inside the echo template.

This module should expose an init function as its default export which will be called immediately
after it was loaded by the browser. It may be a sync or async function since its return is just discarded.

Inside the init function the module is basicly allowed to do whatever but for compatibility's sake it should use the API provided by the global `pnpZone` object.

## `pnpZone` object
```javascript
window.pnpZone = {
	static: String, // base path for accessing static files
	waw: Promise,   // access to waw's Screen object for requesting windows
}
```

## CSS

The main stylesheet for your plugins is attached to `<head>` in the echo template (See go plugin API).

