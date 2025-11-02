
# CSS Position — A to Z Complete Notes (Bangla)

## ✅ Introduction
CSS Position ব্যবহার করা হয় element-কে webpage‑এ নির্দিষ্ট স্থানে রাখার জন্য। এটি control দেয় element কীভাবে move হবে, কিভাবে layer হবে, এবং scroll‑এ কিভাবে behave করবে।

---

## 🎯 Types of Position
CSS‑এ position এর ৫টি ধরন আছে:

1. **static**
2. **relative**
3. **absolute**
4. **fixed**
5. **sticky**

---

## 🧱 1️⃣ position: static (Default)
Static হলো default positioning system.

```css
position: static;
```
- Offset (`top`, `left`, etc) কাজ করে না
- Document flow follow করে

📌 সাধারণ element‑এ ব্যবহৃত হয়।

---

## 📐 2️⃣ position: relative
Element তার **নিজস্ব** অবস্থান থেকে offset হতে পারে।

```css
position: relative;
top: 10px;
left: 20px;
```
✅ Flow ভাঙে না  
✅ Space আগের মতো থাকে

📌 Absolute child‑এর parent হিসাবে ব্যবহৃত হয়।

---

## 🎯 3️⃣ position: absolute
Element normal flow থেকে বের হয়ে যায়।

```css
position: absolute;
top: 0;
right: 0;
```
✅ Parent এ `position: relative` থাকলে ভালো  
✅ Space occupy করে না

📌 Dropdown, tooltip, modal‑এ প্রচুর ব্যবহার।

---

## 📌 absolute Parent Rules
Absolute anchor খুঁজে:
- nearest relative/absolute/fixed/sticky parent
- না পেলে → body

---

## 🧊 4️⃣ position: fixed
Element viewport (browser window)‑এ fixed থাকে।

```css
position: fixed;
bottom: 10px;
right: 10px;
```
✅ Scroll হলেও নড়ে না  
✅ Overlay/Headers‑এ useful

উদাহরণ:
- Chat bubble
- Back to top button

---

## 🪝 5️⃣ position: sticky
Relative + Fixed এর combo। Scroll threshold পার হলে fixed হয়ে যায়।

```css
position: sticky;
top: 20px;
```

✅ Table header, sidebar‑এ দারুণ।

⚠️ Sticky fail করে যখন:
- parent height কম
- overflow hidden থাকে

---

## 🚩 Offset Properties (Top/Right/Bottom/Left)

```css
top: 10px;
left: 20px;
right: 5px;
bottom: 0;
```

👉 Absolute, relative, fixed‑এ কার্যকর।

---

## 🧠 Document Flow Difference

| Position | Flow Follow করে? | Space ধরে রাখে? |
|----------|-------------------|--------------------|
| static   | ✅ | ✅ |
| relative | ✅ | ✅ |
| absolute | ❌ | ❌ |
| fixed    | ❌ | ❌ |
| sticky   | ✅/❌ | ✅ |

---

## 🎨 z-index (Layer Control)

```css
z-index: 99;
```

📌 Higher = উপরে দেখা যাবে  
⚠️ `position: static` হলে কাজ নাও করতে পারে।

---

## 📦 Stacking Context
Layering concept যেখানে browser নির্ধারণ করে কে কার উপর থাকবে।

Trigger করে:
- position + z-index
- opacity < 1
- transform

---

## 🔁 Relative + Absolute Combo (Very Important)

```css
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 0;
  right: 0;
}
```

✅ UI component build‑এ industry standard।

---

## 🎯 Fixed Navbar Example

```css
nav {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 100;
}
```

---

## 📌 Sticky Sidebar Example

```css
.sidebar {
  position: sticky;
  top: 20px;
}
```

---

## 📍 Tooltip Example

```css
.wrapper {
  position: relative;
}
.tooltip {
  position: absolute;
  bottom: 100%;
  left: 50%;
}
```

---

## 🧩 Dropdown Example

```css
.dropdown {
  position: relative;
}
.menu {
  position: absolute;
  top: 100%;
  right: 0;
}
```

---

## 🕶️ Overlay Example

```css
.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0,0,0,0.6);
  z-index: 999;
}
```

---

## 🧠 When to Use Which?

| কাজ | Position |
|------|----------|
| Floating button | fixed |
| Tooltip | absolute |
| Dropdown | absolute |
| Sticky navbar | sticky |
| Minor adjust | relative |
| Default layout | static |

---

## ⚠️ Common Mistakes

❌ relative parent না দিয়ে absolute child ব্যবহার  
❌ Sticky parent overflow hidden  
❌ z-index conflict  
❌ Random fixed elements → scroll blocking

---

## ✅ Best Practices (2025)

✔ Component design‑এ relative+absolute  
✔ Modal‑এ fixed overlay  
✔ Sticky header‑এ `top:0`  
✔ Avoid too many absolute (responsiveness break)

---

## 🧠 Interview Questions

❓ absolute এবং relative এর পার্থক্য কি?  
❓ sticky কিভাবে কাজ করে?  
❓ z-index কেন কাজ নাও করতে পারে?  
❓ flow কি?  
❓ fixed vs sticky difference?  
❓ stacking context define করো।

---

## 🎯 Practice Assignments

✅ Login overlay তৈরি করো fixed দিয়ে  
✅ Sticky sidebar বানাও  
✅ Tooltip বানাও absolute দিয়ে  
✅ Dropdown বানাও relative+absolute দিয়ে  
✅ Overlay popup modal বানাও fixed দিয়ে

---

## 🏁 Conclusion
CSS Position অনেক UI layout‑এ core ভূমিকা পালন করে। এটা ভালোভাবে শিখলে:
- dropdown
- modal
- navbar
- tooltip
- sidebar
সবকিছু সহজ হয়ে যায়।

Happy Coding 🚀🔥
