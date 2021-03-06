# Policy Controlled Features

This document lists policy-controlled features being implemented in browsers. It
is not intended to be a complete list: browsers may choose to implement other
features not in this list. Nor is it intended to be normative: the definitions
of these features all belong in their respective specs.

| Feature name | Default allowlist | Brief Description |
| ------ | ------ | - |
| `camera` | `self` | Controls access to video input devices.|
| `encrypted-media`| `self`|Controls whether `requestMediaKeySystemAccess()` is allowed.|
| `fullscreen`|`self`|Controls whether `requestFullscreen()` is allowed.|
|`geolocation`|`self`| Controls access to Geolocation interface=]. |
|`microphone`|`self` | Controls access to audio input devices. |
|`midi`|`self`|Controls access to `requestMIDIAccess()` method.|
|`payment`|`self`|Controls access to PaymentRequest interface.|
|`speaker`|`self`|Controls access to audio output devices.|
|`vibrate`|`self`|Controls access to `vibrate()` method.|

## Feature Definitions

### camera

The *camera* feature controls access to video input devices requested through the [NavigatorUserMedia interface](https://w3c.github.io/mediacapture-main/getusermedia.html#navigatorusermedia).

If disabled in a document, then calls to [`getUserMedia()`](https://w3c.github.io/mediacapture-main/getusermedia.html#dom-mediadevices-getusermedia()) MUST NOT grant access to video input devices in that document.

* The **feature name** for *camera* is "`camera`"
* The **default allowlist** for *camera* is `["self"]`.

### encrypted-media

The *encrypted-media* feature controls whether [encrypted media extensions](https://w3c.github.io/encrypted-media/) are available.

If disabled in a document, the promise returned by [`requestMediaKeySystemAccess()`](https://w3c.github.io/encrypted-media/#navigator-extension-requestmediakeysystemaccess) must reject with a `NotSupportedError`.

* The **feature name** for *encrypted-media* is "`encrypted-media`"
* The **default allowlist** for *encrypted-media* is `["self"]`.

### fullscreen

The *fullscreen* feature controls whether the [`requestFullscreen()`](https://fullscreen.spec.whatwg.org/#dom-element-requestfullscreen) method is allowed to request fullscreen.

If disabled in any document, the document will not be allowed to use fullscreen. If enabled, the document will be allowed to use fullscreen.

* The **feature name** for *fullscreen* is "`fullscreen`"
* The **default allowlist** for *fullscreen* is `["self"]`.

### geolocation

The *geolocation* feature controls whether the current document is allowed to use the [Geolocation interface](https://dev.w3.org/geo/api/spec-source.html).

If disabled in any document, calls to both [`getCurrentPosition`](https://dev.w3.org/geo/api/spec-source.html#get-current-position) and [`watchPosition`](https://dev.w3.org/geo/api/spec-source.html#watch-position) must result in the error callback being invoked with `PERMISSION_DENIED`.

* The **feature name** for *geolocation* is "`geolocation`"
* The **default allowlist** for *geolocation* is `["self"]`.

### microphone

The *microphone* feature controls access to audio input devices requested through the [NavigatorUserMedia interface](https://w3c.github.io/mediacapture-main/getusermedia.html#navigatorusermedia).

If disabled in a document, then calls to [`getUserMedia()`](https://w3c.github.io/mediacapture-main/getusermedia.html#dom-mediadevices-getusermedia()) MUST NOT grant access to audio input devices in that document.

* The **feature name** for *microphone* is "`microphone`"
* The **default allowlist** for *microphone* is `["self"]`.

### midi

The *midi* feature controls whether the current document is allowed to use the [Web MIDI API](https://webaudio.github.io/web-midi-api/).

If disabled in a document, the promise returned by [`requestMIDIAccess()`](https://webaudio.github.io/web-midi-api/#dom-navigator-requestmidiaccess) must reject with a `DOMException` parameter.

* The **feature name** for *midi* is "`midi`"
* The **default allowlist** for *midi* is `["self"]`.

### payment

The *payment* feature controls whether the current document is allowed to use the [PaymentRequest interface](https://w3c.github.io/browser-payment-api/).

If disabled in a document, then calls to the [`PaymentRequest` constuctor](https://w3c.github.io/browser-payment-api/#constructor) MUST throw a `SecurityError`.

* The **feature name** for *payment* is "`payment`"
* The **default allowlist** for *payment* is `["self"]`.

### speaker

The *speaker* feature controls access to audio output devices requested through the [NavigatorUserMedia interface](https://w3c.github.io/mediacapture-main/getusermedia.html#navigatorusermedia).

If disabled in a document, then calls to [`getUserMedia()`](https://w3c.github.io/mediacapture-main/getusermedia.html#dom-mediadevices-getusermedia()) MUST NOT grant access to audio output devices in that document.

* The **feature name** for *speaker* is "`speaker`"
* The **default allowlist** for *speaker* is `["self"]`.

### vibrate

The *vibrate* feature controls whether the [Vibration API](https://w3c.github.io/vibration/) is allowed to cause device vibration.

If disabled in a document, then calls to the [`vibrate()`](https://w3c.github.io/vibration/#dom-navigator-vibrate) method should silently do nothing. If enabled, the browser may allow the device to vibrate.

* The **feature name** for *vibrate* is "`vibrate`"
* The **default allowlist** for *vibrate* is `["self"]`.
