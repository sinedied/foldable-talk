title: Angular apps for dual-screen devices with ngx-foldable
class: animation-fade
layout: true

.twitter-handle[
  @olivierleplus
]

<!--

Prep:
- 1 Ecran: slides
- 1 Ecran: browser edge avec devtools et demo foldable gallery, ngx-foldable
  * https://sinedied.github.io/ngx-foldable/demo/
  * https://foldable-devices.github.io/demos/battleship/build/
  * https://foldable-devices.github.io/demos/photo-gallery/build/
  * https://github.com/foldable-devices/demos
  * edge://flags/#enable-experimental-web-platform-features
  * https://sinedied.github.io/surface-duo-photo-gallery/
  * https://github.com/sinedied/ngx-foldable
- 1 Ecran: emulateur duo
- 1 Ecran: VS Code avec code demo ngx-foldable gallery sur branche before

Celui la c'est pour mon meetup Angular ;)

# Historique(s) 2min - Yohan
- Web/RD + GameWatch/Nintendo DS
* From desktop first to mobile first
* demain? foldavle first?

# Etat de l'art: c'est pas sec 2min - Olivier
* Window Segment + CSS primitives
* Device Posture
+ question dev

# Comment on dev? 10min - Yohan
- Tools/emulateurs + SETUP EMULATOR
- Polyfills / CS JSS
- Problemes
+ question dev

# NGX foldable/React 10min - Yohan
- Demo gallery app

-->

---

class: left, middle, hide-handle, primary, overlay-dark
background-image: url(./images/duo-banner.jpg)

# .light-text[Building multi-screen experiences for the mobile web]

<!-- .full-layer.light-text.space-left[
  .w-10.responsive[![](./images/ng-nation.png)] Angular Nation
] -->

.full-layer.who.text-right.small.middle.light-text[
  .ms.responsive[![](images/aws-white.png)]
  |
  Olivier Leplus
  |
  @olivierleplus
]

???

Commentaire

---

class: middle, center, hide-handle
# .large[Who am I?]

.table.row.middle[
.col-4.center[
  .w-70.responsive.avatar.tada.animated[![](images/olivier.jpg)]
]
.col-8.bit-larger.left[
  .e[Olivier Leplus]<br>
  .bit-larger[\[ Developer Advocate - .mini-img[![](images/aws.png)] \]]<br>
  .small.em-text[GDE Web, Geek, Community lover]<br>
]
]
.center.bit-larger[
.large.em-text[{]
.fab.fa-twitter[]
.large.em-text[}] .e[@olivierleplus]<br>
]
 
???

---

class: impact
## .large[Dual screen devices?]

---

class: contain, middle
background-image: url(./images/gw.jpg)

--
# .large[1982]

---

class: contain, middle
background-image: url(./images/ds-fat.jpg)

???
tactile!

--
# .large[2004]

---

class: contain, middle
background-image: url(./images/3ds.jpg)

--
# .large[2010]

???
3DS: 2010, has web browser!

---

class: contain
background-image: url(./images/duo.jpg)

???
2020

---

background-image: url(./images/new-devices-dual.jpg)

---

class: impact
## .large[So, where to begin?]

---

class: middle, center
# Another responsive design target?

.center[
  .responsive[![](./images/responsive.png)]
]

---

class: full, middle, center, overlay-dark
background-image: url(./images/experimental.jpg)

# .large[⚠️]
# Experimental APIs ahead

---

<!-- 
# So, media queries it is!

```css
@media (screen-spanning: single-fold-vertical) { ... }
@media (screen-spanning: single-fold-horizontal) { ... }

```

.center[
.w-60.responsive[![](./images/spanning-media-query.svg)]
]

.full-layer.stick-bottom.space-left[
.small.no-margin[
[aka.ms/foldable/css-primitives](https://aka.ms/foldable/css-primitives)<br>[aka.ms/docs/css-primitives](https://aka.ms/docs/css-primitives)
]
]

--->
<!-- 
# Environment variables

.center[
.w-60.responsive[![](./images/css-env-variables.svg)]
]

--->
<!-- 
class: middle, center
# But... things moves fast

--- 
-->

# So, media queries it is!

.col-6.float-left.space-right[
```css
@media (horizontal-viewport-segments:2) 
and 
@media (vertical-viewport-segments:1);
```

.center[
  .w-70.responsive[![](./images/horizontal-viewport.png)]
]
]

.col-6.float-left[
```css
@media (horizontal-viewport-segments:1) 
and 
@media (vertical-viewport-segments:2);
```

.center[
  .w-70.responsive[![](./images/vertical-viewport.png)]
]
]

--

---

class: small-handle,center
# ...opening up new possibilities?
```css
@media (horizontal-viewport-segments:2) and @media (vertical-viewport-segments:2);
```

--
  .w-30.responsive[![](./images/crazy-1.png)]
  <br />
--
  .w-30.up.responsive[![](./images/crazy-2.png)]


---

class: impact
## .large[Let's play a game]

---

```css
@media (horizontal-viewport-segments: 2) {
  body { 
    background-color: yellow; 
  }
}
```
.center[
.responsive[![](./images/screens-list-2.png)]
]

---

```css
@media (horizontal-viewport-segments: 2) {
  body { 
    background-color: yellow; 
  }
}
```

.center[
  .responsive[![](./images/screens-list-2-answer.png)]
]

---


# Environment variables

```css
env(viewport-segment-width <x> <y>);
env(viewport-segment-height <x> <y>);
env(viewport-segment-top <x> <y>);
env(viewport-segment-left <x> <y>);
env(viewport-segment-bottom <x> <y>);
env(viewport-segment-right <x> <y>);
```

.center[
.w-60.responsive[![](./images/env-grid.png)]
]

---

class: impact
## .large[What about the JavaScript side?]

---
<!-- 
# Window Segments API

.full-layer.stick-bottom.space-left[
.small.no-margin.text-left.margin-left[
[aka.ms/foldable/window-segments](https://aka.ms/foldable/window-segments)<br>[aka.ms/docs/window-segments](https://aka.ms/docs/window-segments)
]
]
https://bit.ly/segments-explainer
```js
const screenSegments = window.getWindowSegments();
```

-->
<!-- 
<br>

.center.large[
  👆 *But that was before community feedback...*
]

--->

# Visual Viewport Window Segments API

.full-layer.stick-bottom.space-left[
.small.no-margin.margin-left[
*Explainer: https://bit.ly/segments-explainer*
]
]


```js
const segments = window.visualViewport.segments;
```


---

# Visual Viewport Window Segments API

.full-layer.stick-bottom.space-left[
.small.no-margin.margin-left[
*Explainer: https://bit.ly/segments-explainer*
]
]
```js
const segments = window.visualViewport.segments; // => null || DOMRect[]

if (segments && segments.length > 1) {
  // It's a foldable device !







}
```

---

# Visual Viewport Window Segments API

.full-layer.stick-bottom.space-left[
.small.no-margin.margin-left[
*Explainer: https://bit.ly/segments-explainer*
]
]

```js
const segments = window.visualViewport.segments; // => null || DOMRect[]

if (segments && segments.length > 1) {
  // It's a foldable device !
  for (let i = 0; i < segments.length; i++) {
    console.log(`Screen segment ${i}:`);
    console.log('- width   : ' + segments[i].width);
    console.log('- height  : ' + segments[i].height);
    console.log('- x origin: ' + segments[i].x);
    console.log('- y origin: ' + segments[i].y);
  }
}
```

--

.full-layer.text-right.space-right[
  <div style="height: 7em"></div>
  .w-20.responsive[![](./images/diff-screens.png)]
]

---

# Device Posture API
### [w3.org/TR/device-posture/](https://w3.org/TR/device-posture/)

.full-layer.right.space-right[
.w-30.responsive[![](./images/posture-angle.svg)]
]

- **Device**: single-screen (foldable or not), dual-screen
- **Posture**: no-fold, laptop, flat, tent, tablet, book

.center[
.w-70.responsive[![](./images/postures.png)]
]

---

# Device Posture API

```js
navigator.devicePosture.addEventListener("change", () => {
  console.log(`The current posture is: ${navigator.devicePosture.type}!`);
})
```

---

# Device Posture API

```js
navigator.devicePosture.addEventListener("change", () => {
  console.log(`The current posture is: ${navigator.devicePosture.type}!`);
})
```

```css
@media (device-posture: laptop) and (vertical-viewport-segments: 2) {
  /* Where the magic happens! */
}
```

.center[
.w-30.responsive[![](./images/posture-example-videocall.svg)]
]

---

class: impact, alt
## .large[Demos]

???

- ngx-foldable demo
- gallery app
- battleship

---

class: impact
## .large[Setting up for development]

---

# Enable browser dual-screen emulation
### [aka.ms/foldable/dev-setup](aka.ms/foldable/dev-setup)

1. `chrome://flags` or `edge://flags`
2. Enable **Experimental Web Platform features**
3. Open dev tools settings
4. In **Experiments** tab, tick **Emulation: Support dual screen mode**

.center[
  .w-70.responsive[![](./images/edge-flags.png)]
]

---

# Android Surface Duo emulator
### [aka.ms/foldable/dev-setup](https://aka.ms/foldable/dev-setup)

.center[
  .w-90.responsive[![](./images/duo-emu.png)]
  ### ⚠️ *Highly recommended!*
]

---

class: middle, hide-handle

.big-text.no-bg.baseline[
```js
const end = {
  message: 'Thank you!',
  links  : 'aka.ms/ngx-foldable'
};

alert('Questions?');
```
]

<hr class="hr-right more-space">
.right.large[
.large.em-text[{]
.fab.fa-twitter[]
.large.em-text[}] .e[@olivierleplus]<br>
]
