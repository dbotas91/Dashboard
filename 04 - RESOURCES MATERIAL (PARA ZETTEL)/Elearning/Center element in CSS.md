---
tags:
  - elearning
dg-publish: "true"
dg-note-icon: lackluster
noteIcon: lackluster
---
# Center element in CSS

|   |   |
|---|---|
|![](list_gray%2031.svg)Content Type|Code snippets|
|![](list_gray%2031.svg)Topic|Front end|
|![](link_gray%2018.svg)Link|[https://css-tricks.com/centering-css-complete-guide/](https://css-tricks.com/centering-css-complete-guide/)|
|![](clock_gray%208.svg)Created time|@February 7, 2022 11:44 AM|
|![](checkmark-square_gray%208.svg)Finished||

# ↔️ Horizontally

**Inline elements**

**Block level elements**

```CSS
.center {
  text-align: center;
}
```

```CSS
.center-me {
  margin: 0 auto;
}
```

---

# ↕️ Vertically

**Inline elements**

**Block level elements**

```CSS
.center {
  text-align: center;
}
```

```CSS
.center-me {
  margin: 0 auto;
}
```

---

# 🔄 Horizontally and vertically

**Fixed width and height**

**Flexbox method**

```CSS
.parent {
  position: relative;
}

.child {
  width: 300px;
  height: 100px;
  padding: 20px;

  position: absolute;
  top: 50%;
  left: 50%;

  margin: -70px 0 0 -170px;
}
```

```CSS
.parent {
  display: flex;
  justify-content: center;
  align-items: center;
}
```