# Waw API

Waw is the window manager used for pnp-zone when the ui is to complex to show everything at once.

Its API consists of a single class `Screen` which is effectively a singleton managing your whole html's body.

## `Screen`

### `constructor(parent)`

Create a new instance which renders its content (i.e. windows) it the given parent element.

`pnp-zone` instantiates one rendering into `<body>` and exposes it in the global `pnpZone` object.
See [Javascript API](./js.md).

### `newWindow({dock, icon, title})`

Request a new window

This returns a `Promise` which resolves to a `<div/>` to fill with your content.

| Option  | Type                                               | Required |
|---------|----------------------------------------------------|----------|
| `dock`  | "top" \| "left" \| "bottom" \| "right" \| "center" | Yes      |
| `icon`  | Url as String                                      | No       |
| `title` | String                                             | No       |

### `resize()`

Force redrawing after quering the parent's dimensions.

Doesn't really do anything yet.

### `destroy()`

Delete the screen and all its windows.

