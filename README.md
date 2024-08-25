# Vue Simple Toast Demo

This project is a quick Demo for a Toast component.

I added the **container** for the Toast Events directly in the App, as an Unordered List.
The list has a fixed position so we can move around based on the Viewport. Depending on where it may be used, this positioning should most likely be absolute, based on a relative *content container*.

The Toast Event component is mostly JS and CSS to animate the appearance of the event, as well as emit a *close* event so the list knows when to remove an item.
