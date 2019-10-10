
## Installation
You can install the latest release using npm:
```bash
npm install --save signature_pad
```
or Yarn:
```bash
yarn add signature_pad
```

You can also add it directly to your page using `<script>` tag:
```html
<script src="https://cdn.jsdelivr.net/npm/signature_pad@2.3.2/dist/signature_pad.min.js"></script>
```
You can select a different version at [https://www.jsdelivr.com/package/npm/signature_pad](https://www.jsdelivr.com/package/npm/signature_pad).

This library is provided as UMD (Universal Module Definition) and ES6 module.

**NOTE** When importing this library in TypeScript, one needs to use the following syntax:
```js
import * as SignaturePad from 'signature_pad';
```
For more info why it's needed, check these 2 issues: [TypeScript#13017](https://github.com/Microsoft/TypeScript/issues/13017) and [rollup#1156](https://github.com/rollup/rollup/issues/1156).

## Usage
### API
``` javascript
var canvas = document.querySelector("canvas");

var signaturePad = new SignaturePad(canvas);

// Returns signature image as data URL (see https://mdn.io/todataurl for the list of possible parameters)
signaturePad.toDataURL(); // save image as PNG
signaturePad.toDataURL("image/jpeg"); // save image as JPEG
signaturePad.toDataURL("image/svg+xml"); // save image as SVG

// Draws signature image from data URL.
// NOTE: This method does not populate internal data structure that represents drawn signature. Thus, after using #fromDataURL, #toData won't work properly.
signaturePad.fromDataURL("data:image/png;base64,iVBORw0K...");

// Returns signature image as an array of point groups
const data = signaturePad.toData();

// Draws signature image from an array of point groups
signaturePad.fromData(data);

// Clears the canvas
signaturePad.clear();

// Returns true if canvas is empty, otherwise returns false
signaturePad.isEmpty();

// Unbinds all event handlers
signaturePad.off();

// Rebinds all event handlers
signaturePad.on();
```
