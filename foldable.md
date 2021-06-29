title: Les web apps multi écran, c'est pas sec... mais on s'est jeté à l'eau
class: animation-fade
layout: true

.twitter-handle[
  @sinedied | @olivierleplus
]

<!--

# Historique(s) 5min - Yohan
- Web/RD + GameWatch/Nintendo DS
* From desktop first to mobile first
* demain? foldavle first?

# Etat de l'art: c'est pas sec 5min - Olivier
* Window Segment + CSS primitives
* Device Posture
+ question dev

# Demo: plouf 10min - Olivier
Vanilla HTML/JS/CSSx

# UI/patterns 5min / tous les 2 / images
* discussion? qu'est ce que vous avez en tete?
 * list/detail
 * 1 ecran a la fois
 * twitch + comments
 * jeux videos/MK/bataille navale
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

class: left, hide-handle
background-image: url(images/dive.jpg)

.title[
# .large.light-text[Les web apps multi-écrans]
## C'est pas sec... mais on s'est jeté à l'eau!
]

.full-layer.who.text-right.small.middle.light-text[
  .ms.responsive[![](images/ms-full-logo.svg)]
  |
  Yohan Lasorsa
  |
  Olivier Leplus
]

???

Commentaire

---

class: center, middle
# Who are we?

.table.row.middle.center[
.col-2[]
.col-4.center[
  .w-70.responsive.avatar.bounceInLeft.animated[![](images/photo.jpg)]

  **Yohan Lasorsa**<br>
  .fab.fa-twitter[] .e[@sinedied]
]
.col-4.center[
  .w-70.responsive.avatar.bounceInUp.animated[![](images/olivier.jpg)]

  **Olivier Leplus**<br>
  .fab.fa-twitter[] .e[@olivierleplus]
]
]

---

class: impact
## .big.book[Once upon a time...]

---

class: contain
background-image: url(./images/web-before.jpg)

???
~ 1960-2000

---

class: impact
## .large.book[Then came new devices...]

---

class: contain, hide-handle
background-image: url(./images/web-after.jpg)

???
- 2007 Iphone
- 2008 Android

---

class: impact
## .large.book[And someone had an idea.]

---

class: middle, center
.script.big-text[
.quote[
> .book.small[Your web apps shall be responsive!]
]
]

???
2010

---

class: impact
## .large.book[Responsive design was born.]

---

class: impact
## .large.book[But something wasn't right!]

---

class: contain
background-image: url(./images/desktop-first.png)

---

class: impact
## .large.book[Someone else had *another* idea.]

---

background-image: url(./images/drake-mobile.png)

???
2011

---

class: impact
## .large.book[Then came new devices.]

---

class: contain
background-image: url(./images/ds-fat.jpg)

---

class: impact

.row.table.middle[
.col-1[
  .big[.big[.big.book[(]]]
]
.col-10[
## .book.bit-smaller[Actually, this a bit wrong.]
## .small.book[This one came even before the mobile web.]
]
.col-1[
  .big[.big[.big.book[)]]]
]
]

???
NDS: 2004

---

class: contain
background-image: url(./images/3ds.jpg)

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
## .large.book[What if...]

---

class: contain, dark, hide-handle
background-image: url(./images/dual-first.jpg)

---

class: impact
## .larger[What about UI/UX?]

---

class: middle, center
# Design patterns? 🤔

???
Quelles sont vos idées?

---

# List / details

---

# Visualize + interact

- 1 screen to view content
- 1 screen to interact with it

Twitch + comments, keyboard...

---

# Alternate view

Batteleship (Mine+yours), Mario kart (main+map)

---

# Split interaction

2 DJ mixers


---

class: middle, hide-handle

.big-text.no-bg.baseline[
```js
const end = {
  message: 'Thank you!',
  slides : 'bit.ly/everypwa',
  link   : 'aka.ms/gopwa' // Get started with PWA
};

alert('Questions?');
```
]

<hr class="hr-right more-space">
.right.large[
.large.em-text[{]
.fab.fa-twitter[] .fab.fa-github[] .fab.fa-dev[]
.large.em-text[}] .e[@sinedied]<br>
]

---

exclude: true
class: hide-handle, dark, light-text

.side-layer.right[
  <div style="height: 5.5em"></div>
  .w-30.responsive[![](images/bit-learning.png)]
]

# References
- [HackerNews PWA comparison](https://hnpwa.com)
- [PWA @ Google Developers](https://developers.google.com/web/progressive-web-apps/)
- [PWA 101](https://www.freecodecamp.org/news/progressive-web-apps-101-the-what-why-and-how-4aa5e9065ac2/)
- [PWA, welcome to the mobile revolution](https://www.creativebloq.com/features/pwas-welcome-to-the-mobile-revolution)
- [PWA support & compatibility](https://medium.com/@guillaumeandre/progressive-web-app-pwa-support-et-compatibilite-manifest-39bcfc703737)
- [The modern PWA cheat sheet (slides)](https://www.slideshare.net/firt/the-modern-pwa-cheat-sheet)
- [PRPL pattern](https://developers.google.com/web/fundamentals/performance/prpl-pattern/)
- [TWA for Google Play Store](https://medium.com/@firt/google-play-store-now-open-for-progressive-web-apps-ec6f3c6ff3cc)
- https://serviceworke.rs
- https://www.pwabuilder.com
- https://github.com/TalAter/awesome-service-workers
