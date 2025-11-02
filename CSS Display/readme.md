
# CSS Display Property — A to Z Complete Notes (Bangla)

## ✅ Introduction
CSS `display` property ব্যবহার করা হয় element-এর **layout behavior** কন্ট্রোল করতে। 
এটি নির্ধারণ করে element কিভাবে page-এ render হবে, box model কেমন behave করবে,
এবং অন্যান্য element এর সাথে সম্পর্ক কী হবে।

---

## 🎯 Why Display Matters?
- Layout structure control
- Inline/Block behavior
- Responsive design
- Flex/Grid activation
- UI component architecture

---

## 📌 Display Property Values (Most Important)

### 1️⃣ `display: block;`
- পুরো width নেয় (100%)
- নতুন লাইনে নেয়
- width/height/margin/padding fully work

```css
display: block;
```
✅ Ex: `div`, `p`, `h1`, `section`

---

### 2️⃣ `display: inline;`
- Width/height set করা যায় না
- শুধু content এর width নেয়
- একই লাইনে থাকে

```css
display: inline;
```
✅ Ex: `span`, `a`, `strong`

---

### 3️⃣ `display: inline-block;`
Hybrid behavior:
- Inline-এর মতো লাইনে থাকে
- Block-এর মতো width/height কাজ করে

```css
display: inline-block;
```
✅ Best for button UI

---

### 4️⃣ `display: none;`
Element hide করে completely:
- Layout থেকে remove হয়ে যায়
- Space occupy করে না

```css
display: none;
```
✅ Menu toggle, modal hide, responsive UI

---

### 5️⃣ `display: flex;`
Flexbox layout activate করে
```css
display: flex;
```
- Alignment easy
- Space distribution easy

✅ 1D layout (Row/Column)

---

### 6️⃣ `display: grid;`
Grid layout activate করে
```css
display: grid;
```
✅ 2D layout (Row + Column)

---

### 7️⃣ `display: inline-flex;`
Inline element-এর মতো লাইনে থাকে, কিন্তু flex behavior রাখে

```css
display: inline-flex;
```

---

### 8️⃣ `display: inline-grid;`
```css
display: inline-grid;
```
Grid + inline behavior

---

### 9️⃣ `display: table;`
Table-এর মতো behave করে

```css
display: table;
```
✅ Used in legacy layouts

---

### 🔟 `display: table-row;`
```css
display: table-row;
```

### 1️⃣1️⃣ `display: table-cell;`
```css
display: table-cell;
```
Old method vertical-align এর জন্য

---

### 1️⃣2️⃣ `display: contents;`
Child elements render হবে কিন্তু parent box remove হবে
```css
display: contents;
```
✅ Useful for accessibility

---

### 1️⃣3️⃣ `display: list-item;`
Ordered/Unordered list behavior

```css
display: list-item;
```

✅ Bullet থাকে

---

### 1️⃣4️⃣ `display: block-flow;` (rare)
Experimental flow layouts

---

## 🧠 Inline vs Block (Very Important)

| Feature | Inline | Block |
|--------|--------|--------|
| Line breaks | ❌ | ✅ |
| Width control | ❌ | ✅ |
| Height control | ❌ | ✅ |
| Full width | ❌ | ✅ |

---

## 📐 Inline-block Benefits
✅ Inline without line break
✅ Control width & height
✅ Good for navigation menus

---

## 🚫 display:none vs visibility:hidden

| Feature | display:none | visibility:hidden |
|--------|---------------|-------------------|
| Space keeps? | ❌ | ✅ |
| Accessible? | ❌ | ✅ |

```css
visibility: hidden;
```

---

## 🎉 Real Use Cases

### ✅ Hide Element
```css
display: none;
```

### ✅ Show in mobile only
```css
@media(max-width: 600px){
  .box { display:block; }
}
```

### ✅ Inline navbar items
```css
li { display: inline-block; }
```

---

## 🔥 Important Concept: Formatting Context

Some display values create new formatting contexts like:
- flex container
- grid container
- table layout

👉 এগুলো child element-এর behavior completely change করে

---

## 🧩 display: block-flow-root (Modern CSS)
Clear float automatically

```css
display: flow-root;
```

✅ No clearfix hacks!

---

## 🛠️ Performance Tip
Frequent `display:none;` DOM heavy element-এ avoid করো  
Instead → visibility

---

## 🧠 Interview Questions

❓ difference inline vs inline-block?
❓ display:none vs visibility:hidden?
❓ flex vs inline-flex?
❓ block vs inline flow?
❓ Why display matters in layout?

---

## 🎯 Best Practices (2025)

✔ Navbar: `inline-block` / `flex`
✔ Complex Layout: `grid`
✔ Card alignment: `flex`
✔ Accessibility: `contents`
✔ Avoid table layouts (old)

---

## 🧩 Cheatsheet

```css
display: block;
display: inline;
display: inline-block;
display: none;

display: flex;
display: inline-flex;

display: grid;
display: inline-grid;

display: table;
display: table-row;
display: table-cell;

display: contents;
display: flow-root;
```

---

## 🏁 Conclusion
`display` হলো CSS layout-এর মূল ভিত্তি।  
এটা না জানলে flex/grid/styling সঠিকভাবে কাজে লাগে না।

Master this → layout king 👑

Happy Coding 🚀🔥
