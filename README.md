# Polyfill for CSS `background-opacity`

This is a proof of concept for polyfilling a hypothetical CSS property called `background-opacity`.

Inspired by [Hugo Giraudel's tweet](https://twitter.com/hugogiraudel/status/909701601232867328);

[Live demo](https://oslego.github.io/background-opacity-polyfill)

## Method
- get computed style of element `background-image`;
- if it's an image, draw it onto a `<cavnas>` element;
- set canvas context `globalAlpha` value to `background-opacity` value;
- encode canvas with `.toDataURL()`;
- replace element `background-image` with encoded canvas.

## To Consider
- account for multiple background images
- when background image is a gradient, mutate color stops to account for `background-opacity`
