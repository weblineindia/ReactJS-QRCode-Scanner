# ReactJS - QR Code / Barcode Scanner Component

ReactJS based QR Code Scanner component, allowing you to detect and decode QR codes.

## Table of contents

- [Browser Support](#browser-support)
- [Getting started](#getting-started)
- [Usage](#usage)
- [Available Props](#available-props)
- [Methods](#methods)
- [Want to Contribute?](#want-to-contribute)
- [Collection of Components](#collection-of-components)
- [Changelog](#changelog)
- [Credits](#credits)
- [License](#license)
- [Keywords](#Keywords)

## Browser Support

| ![Chrome](https://raw.github.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) | ![Firefox](https://raw.github.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) | ![Safari](https://raw.github.com/alrra/browser-logos/master/src/safari/safari_48x48.png) | ![Edge](https://raw.github.com/alrra/browser-logos/master/src/edge/edge_48x48.png) | ![IE](https://raw.github.com/alrra/browser-logos/master/src/archive/internet-explorer_9-11/internet-explorer_9-11_48x48.png) |
| ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 83.0 ✔                                                                                   | 77.0 ✔                                                                                      | 13.1.1 ✔                                                                                 | 83.0 ✔                                                                             | Not supported                                                                                                                       |


## Getting started

Install the npm package:

``` bash
npm install react-weblineindia-qrcode-scanner
#OR
yarn add react-weblineindia-qrcode-scanner
```

## Usage

Use the `<react-weblineindia-qrcode-scanner>` component:

```js
import React, { Component } from 'react'
import QrReader from 'react-weblineindia-qrcode-scanner'

class Test extends Component {
  constructor(props){
    super(props)
    this.state = {
      delay: 100,
      result: 'No result',
    }

    this.handleScan = this.handleScan.bind(this)
  }
  handleScan(data){
    this.setState({
      result: data,
    })
  }
  handleError(err){
    console.error(err)
  }
  render(){
    const previewStyle = {
      height: 240,
      width: 320,
    }

    return(
      <div>
        <QrReader
          delay={this.state.delay}
          style={previewStyle}
          onError={this.handleError}
          onScan={this.handleScan}
          />
        <p>{this.state.result}</p>
      </div>
    )
  }
}

```
For Next.js Use dynamic import instead of usual import.

```js

import dynamic from 'next/dynamic'
const QrReader = dynamic(() => import('react-weblineindia-qrcode-scanner').then((a) => a.QrReader), {ssr: false});

```


## Available Props

| Prop | Type | default | Description |
| --- | --- | --- | --- |
| delay | number | 500  |The delay between scans in milliseconds. To disable the interval pass in `false`. |
| facingMode | string |   |Specify which camera direction should be used (if available). Options: `front` and `rear`. |
| legacyMode | boolean |false | If the device does not allow camera access (e.g. IOS Browsers, Safari) you can enable legacyMode to allow the user to take a picture (On a mobile device) or use an existing one. To trigger the image dialog just call the method `openImageDialog` from the parent component. **Warning** You must call the method from a user action (eg. click event on some element).|
| maxImageSize | number | 1500   |  If `legacyMode` is active then the image will be downscaled to the given value while keepings its aspect ratio. Allowing larger images will increase the accuracy but it will also slow down the processing time.|
| style | object |   | Styling for the preview element. This will be a `video` or an `img` when `legacymode` is `true`. **Warning** The preview will keep its aspect ratio, to disable this set the CSS property [objectFit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) to `fill`.|
| className | string |   | ClassName for the container element.  |
| chooseDeviceId | function |   | Called when choosing which device to use for scanning. By default chooses the first video device matching `facingMode`, if no devices match the first video device found is choosen. |


## Methods

| Name | Description |
| --- | --- |
| onScan | Scan event handler. Called every scan with the decoded value or `null` if no QR code was found. |
| onError | Function to call when an error occurs such as:- Not supported platform -The lack of available devices |
| onLoad | Called when the component is ready for use. |
| onImageLoad | Called when the image in legacyMode is loaded. |


## Want to Contribute?

- Created something awesome, made this code better, added some functionality, or whatever (this is the hardest part).
- [Fork it](http://help.github.com/forking/).
- Create new branch to contribute your changes.
- Commit all your changes to your branch.
- Submit a [pull request](http://help.github.com/pull-requests/).

---

## Collection of Components

We have built many other components and free resources for software development in various programming languages. Kindly click here to view our [Free Resources for Software Development](https://www.weblineindia.com/software-development-resources.html)

------

## Changelog

Detailed changes for each release are documented in [CHANGELOG.md](./CHANGELOG.md).

## Credits

react-weblineindia-qrcode-scanner  is inspired by [react-qr-scanner](https://www.npmjs.com/package/react-qr-scanner).

## License

[MIT](LICENSE)

[mit]: https://github.com/weblineindia/ReactJS-QRCode-Scanner/blob/master/LICENSE

## Keywords

react-weblineindia-qrcode-scanner, qrcode, qrcode-reader, qrcode-scanner, webrtc, react-qrcode-scanner, barcode-scanner, react-barcode, reactjs-qr-code, reactjs-barcode
