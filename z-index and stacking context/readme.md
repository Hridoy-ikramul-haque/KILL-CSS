
# 🔼 CSS Z-index & Stacking Context — A to Z Full Notes (Bangla)

## ✅ Introduction
`z-index` ব্যবহার করা হয় কোন element সামনে (top) বা পেছনে (back) থাকবে তা নির্ধারণ করার জন্য।  
ওভারল্যাপ problem solve করতে এটা খুবই গুরুত্বপূর্ণ।

---

## 🎭 What is Z-index?
Web page 2D layout হলেও element গুলো overlap করলে 3D stacking order তৈরি হয়।  
`z-index` সেই order control করে।

---

## 📌 Default behavior
যে element HTML‑এ **later** আসে → সাধারণত সামনে থাকে।

---

## ⭐ When does z-index work?
`z-index` তখনই কাজ করে যখন element‑এর `position` হয়:
- relative
- absolute
- fixed
- sticky

```css
position: relative;
z-index: 5;
```

❌ static element‑এ `z-index` কাজ করবে না।

---

## 🕋 Stacking Context (Very Important)
Stacking context হলো layered environment যেখানে elements নিজেদের মধ্যে z‑ordering করে।  
একটি নতুন stacking context হলে তার child বাইরে প্রভাব ফেলতে পারে না।

---

## 🧱 How stacking context is created?

1. `position` + `z-index` (non‑auto)
```css
position: relative;
z-index: 1;
```

2. `opacity < 1`
```css
opacity: 0.9;
```

3. `transform`
```css
transform: scale(1);
```

4. `filter`
```css
filter: blur(0);
```

5. `isolation: isolate`
6. `mix-blend-mode`
7. `will-change`
8. `flex` / `grid` child with `z-index`

✅ এগুলো stacking context create করে।

---

## 🔒 Why stacking context matters?
Child element **cannot** come above the parent's parent!
(Cannot escape its stacking context)

Example:
Modal inside lower z‑container → overlay bug

---

## 💣 Common Bug
`position: relative` & `z-index` না থাকলে overlay কাজ করবে না।

---

## 🔥 Basic Example
```css
.box1 {
  position: relative;
  z-index: 10;
}

.box2 {
  position: relative;
  z-index: 5;
}
```
👉 box1 সামনে থাকবে।

---

## ⚠️ opacity trap!
```css
.parent {
  opacity: 0.99; /* creates stacking context */
}
```
এর child আর বাইরে উঠতে পারবে না।

---

## 🧩 transform trap!
```css
.parent {
  transform: translateZ(0);
}
```
এটিও stacking context তৈরি করে।

---

## 🧠 Order of stacking (lowest → highest)

1. Background/border
2. Positioned z‑auto descendants
3. Positioned z‑positive
4. Non‑positioned inline/blocks
5. Higher z‑index positioned

---

## 🎯 Why z-index not working?
Possible reasons:
- Parent stacking context
- Position missing
- Z-index too low
- Browser rendering order

---

## ✅ Fix Example
```css
.parent {
  position: relative;
  z-index: 10;
}

.child {
  position: absolute;
  z-index: 999;
}
```

---

## 🧱 Z-index & Flexbox
Flex item‑এ z‑index কাজ করবে if:
```css
position: relative;
```

---

## 🧱 Z-index & Grid
Grid child‑এও একই rules।

---

## 📐 Negative Z-index
Element completely behind other content
```css
z-index: -1;
```

⚠️ Sometimes may go behind page background.

---

## 🛡️ isolation: isolate (Pro)
Child stacking context leak prevent

```css
.container {
  isolation: isolate;
}
```

---

## 🧠 Stacking Context Debug Checklist

✅ Element positioned?  
✅ Parent stacking context আছে?  
✅ opacity/transform causing stacking?  
✅ z-index positive?  
✅ devtools overlay check?  

---

## 🧪 Z-index in components
- Modal → High z (9999)
- Dropdown → Higher than header (1000+)
- Tooltip → Higher than dropdown (1100)
- Notification → Topmost

---

## ✅ Pro Tip: Variable z-index System
```css
:root {
  --z-back: -1;
  --z-base: 1;
  --z-header: 100;
  --z-dropdown: 1000;
  --z-modal: 2000;
  --z-toast: 3000;
}
```

---

## 🧠 Position + Z-index Summary Table

| position | z-index works? |
|----------|-----------------|
| static | ❌ |
| relative | ✅ |
| absolute | ✅ |
| fixed | ✅ |
| sticky | ✅ |

---

## 🔥 Stacking Context Examples

### New context via opacity
```css
.card {
  opacity: 0.99;
}
```

### via transform
```css
.card {
  transform: translateY(0);
}
```

---

## 🎥 Modal Bug Example
Child modal can't go above parent:
Parent created stacking context → modal stuck.

Fix:
```css
modal-container { position: fixed; }
```

---

## 🚀 Real World Use Cases
✅ Dropdown over content  
✅ Tooltip on hover  
✅ Modal overlay  
✅ Notification toast  
✅ Sticky header overlap fix  

---

## 💡 Debug Tools
Chrome DevTools → Layers panel

---

## 🧠 Interview Questions
❓ What creates stacking context?  
❓ Why z-index sometimes fails?  
❓ What is stacking order?  
❓ Difference negative vs positive z-index?  
❓ How transform affects stacking?  

---

## 🏁 Conclusion
Z‑index = Layer control  
Stacking Context = Layer boundary

Master these → zero overlap bugs ✅  
Professional UI guaranteed 🔥

Happy Layering 🚀
