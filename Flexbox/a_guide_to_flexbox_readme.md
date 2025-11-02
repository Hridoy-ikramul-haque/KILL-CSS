
# Flexbox সম্পূর্ণ গাইড — A to Z (Bangla)

> এই README-টি **CSS-Tricks** এর "A Complete Guide to Flexbox" এবং MDN-কে রেফারেন্স হিসেবে নিয়ে (পরিশেষে) বাংলায় সহজ, সম্পূর্ণ ও অনূদিত **অরিজিনাল** নোট হিসেবে তৈরি করা হয়েছে।
> (আমি মূল লেখার সরাসরি অনুবাদ করিনি — বরং একই বিষয়গুলোকে সহজ এবং ব্যবহারযোগ্য বাংলায় পুনর্লিখন করেছি)।
>
> রেফারেন্স: CSS-Tricks, MDN. citeturn1search0turn1search13

---

## ✅ পরিচিতি
Flexbox (Flexible Box Layout) হলো CSS-এর একটি মডিউল যা container-এর ভিতরের items-গুলোকে একটি এক-দিক (row/column) বরাবর সহজে সাজাতে, align করতে এবং available space distribute করতে সাহায্য করে। সেটি responsive layout বানাতে খুবই উপযোগী। citeturn1search0

---

## সূচিপত্র (Table of contents)
1. Background — কেন Flexbox?  
2. Terminology — Main axis, Cross axis, Flex lines  
3. Parent properties (Flex container) — প্রতিটি property ব্যাখ্যা  
4. Child properties (Flex items) — প্রতিটি property ব্যাখ্যা  
5. Common patterns & examples — practical snippets  
6. Browser support & prefixing (short)  
7. Flexbox tricks and pitfalls  
8. Resources & further reading

---

## 1) Background — কেন Flexbox ব্যবহার করব?
- নতুন UI তৈরিতে, যেখানে element-গুলোকে centre করা, spacing ও alignment control করা দরকার, সেখানে Flexbox খুব উপযোগী।  
- প্রাচীন float বা inline-block hacks এর থেকে বেশি predictable ও শক্তিশালী। citeturn1search0

---

## 2) Basics & Terminology
- **Flex container**: যে element-এ `display: flex` বা `inline-flex` দেয়া আছে।  
- **Flex items**: container-এর সরাসরি children।  
- **Main axis**: `flex-direction` দ্বারা নির্ধারিত প্রধান অক্ষ (default: row)।  
- **Cross axis**: main axis-এর উল্টো দিকে (vertical যদি main axis horizontal হয়)।  
- **Flex line**: একটি row/column where items are placed (wrapping করলে একাধিক line হতে পারে)।

---

## 3) Flex Container Properties (Parent)
নীচে প্রতিটি property-এর অনুধাবন ও ব্যবহারের উদাহরণ দেওয়া হল — copy-paste করতে পারো।

### display
```css
.container { display: flex; }
/* বা inline-flex */
```
- `flex` করলে element টি block-level flex container হবে। `inline-flex` করলে inline flex behavior পাবে। citeturn1search0

### flex-direction
```css
.flex { flex-direction: row; } /* default */
.flex-col { flex-direction: column; }
.flex-row-rev { flex-direction: row-reverse; }
```
- নির্ধারণ করে main axis কে কোথায় ধরবে।

### flex-wrap
```css
.flex-wrap { flex-wrap: wrap; }
.flex-nowrap { flex-wrap: nowrap; } /* default */
.flex-wrap-reverse { flex-wrap: wrap-reverse; }
```
- items কিভাবে wrap করবে তা control করে।

### flex-flow
- Shorthand: `flex-flow: <direction> <wrap>;`  
```css
.flex { flex-flow: row wrap; }
```

### justify-content (main-axis alignment)
```css
justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
```
- Horizontal বা main-axis-এ items কিভাবে distribute হবে তা নির্ধারণ করে।

### align-items (cross-axis alignment)
```css
align-items: stretch | flex-start | flex-end | center | baseline;
```
- Single-line container-এ cross-axis alignment control করে।

### align-content (multi-line alignment)
```css
align-content: stretch | flex-start | flex-end | center | space-between | space-around;
```
- wrapping হলে multiple lines কিভাবে distribute হবে তা নির্ধারণ করে।

### gap (space between items)
```css
gap: 16px; /* row-gap / column-gap আলাদাভাবে দেয়া যায় */
```
- Flexbox-এ modern `gap` property use করা যেতে পারে। (পুরোনো ব্রাউজারে gap না কাজ করলে margin hacks ব্যবহার করা লাগতে পারে)

---

## 4) Flex Item Properties (Children)
### order
```css
.item { order: 2; }
```
- smaller order value প্রথমে দেখায়। DOM order না বদলে ভিজ্যুয়াল order পরিবর্তন করে।

### flex-grow
```css
.item { flex-grow: 1; }
```
- leftover space থাকলে কতো অনুপাতে grow করবে তা বলে। Default 0।

### flex-shrink
```css
.item { flex-shrink: 1; }
```
- space কমলে items কতটুকু shrink করবে। Default 1।

### flex-basis
```css
.item { flex-basis: 200px; } /* initial main size */
```
- item-এর initial size নির্ধারণ করে, তার পরে `flex-grow`/`flex-shrink` কাজ করে।

### flex (shorthand)
```css
.item { flex: 1 1 200px; } /* grow shrink basis */
```
- `flex` shorthand খুবই common — `flex: 1` মানে `flex: 1 1 0%` (grow enabled) — তবে ব্রাউজার অনুযায়ী subtle differences থাকতে পারে।

### align-self
```css
.item { align-self: center; }
```
- single item-কে parent-এর `align-items` থেকে আলাদা করে align করে। Values: `auto | flex-start | flex-end | center | baseline | stretch`.

---

## 5) Common Patterns & Examples (প্রয়োগযোগ্য কোড)

### A. Horizontal center + vertical center (viewport centered box)
```html
<div class="wrap">
  <div class="box">Centered</div>
</div>
```
```css
.wrap {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}
```

### B. Simple nav (left logo, center links, right actions)
```css
nav { display: flex; align-items: center; }
.logo { margin-right: auto; } /* pushes other items */
.actions { margin-left: auto; }
```

### C. Equal width columns
```css
.container { display: flex; }
.container > * { flex: 1; } /* equal widths */
```

### D. Responsive wrapping cards
```css
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}
.card { flex: 1 1 250px; } /* grow, shrink, base 250px */
```

### E. Stacked layout for small screens
Use media queries:
```css
@media (max-width: 600px) {
  .row { flex-direction: column; }
}
```

---

## 6) Examples, Tricks & Useful Tips
- Use `margin: auto` on flex items for precise alignment (e.g., centering a single item or pushing an item to one side).  
- For vertical centering of unknown-height children, Flexbox is simpler than older techniques.  
- `gap` is cleaner than per-item margins.

---

## 7) Browser Support & Prefixing (short)
- Modern browsers broadly support Flexbox. Legacy prefixes (`-webkit-`) were required in older iOS/Android browsers; nowadays you only need them for very old devices. For compatibility checks, refer to MDN or Can I Use. citeturn1search13turn1search0

---

## 8) Common Pitfalls & How to Fix
- **Unexpected item sizing**: check `flex-basis` and `min-width`/`max-width`.  
- **Overflow on small screens**: use `flex-wrap: wrap` or adjust basis.  
- **Order confusion**: order only changes visual flow; DOM order still used for accessibility/keyboard navigation.  
- **align-content has no effect on single-line flex containers** — only for multi-line.

---

## 9) Further Reading & Tools
- CSS-Tricks: A Complete Guide to Flexbox. citeturn1search0  
- MDN Flexbox documentation. citeturn1search13  
- Interactive learning: Flexbox Froggy (game)

---

## 10) Quick Cheatsheet (copy-paste snippet)
```css
/* Container */
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
  align-items: center;
}

/* Item */
.item {
  flex: 1 1 200px;
  order: 0;
  align-self: auto;
}
```

---

## License & Note
এই README-টি মূল CSS-Tricks লেখা থেকে অনুপ্রাণিত, কিন্তু এখানে আমি বিষয়গুলোকে সংক্ষিপ্ত ও বাংলায় পুনর্লিখন করেছি — কোন সরাসরি দীর্ঘ অনুবাদ বা verbatim পুনরাবৃত্তি করা হয়নি। মূল গাইড পড়তে চাইলে: https://css-tricks.com/snippets/css/a-guide-to-flexbox/ । citeturn1search0

Happy Flexing! 🚀
