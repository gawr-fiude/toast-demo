# Vue Simple Toast Demo

This project is a quick Demo for a Toast component.

## Container

I added the **container** for the Toast Events directly in the App, as an Unordered List.
The list has a fixed position so we can move around based on the Viewport. Depending on where it may be used, this positioning should most likely be absolute, based on a relative *content container*.

## Component

The Toast Event component is mostly JS and CSS to animate the appearance of the event, as well as emit a *close* event so the list knows when to remove an item.
You'll notice the CSS for the component may not be ideal, but it works and is not that hard to read.

## Notes

1. The transition after the event removal needs to be smoothed. I am currently just removing the event from an array.
2. There are a few Toast components in different Component Libraries. You can check [Prime Vue's](https://github.com/primefaces/primevue/tree/master/packages/primevue/src/toast) for a more elegant solution.
