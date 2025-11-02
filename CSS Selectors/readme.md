
# 🎯 CSS Selectors — Pro Level Full Notes (Bangla)

## ✅ Introduction
CSS Selector ব্যবহার করা হয় কোন HTML element কে target করে style apply করার জন্য।  
Selectors ভালোভাবে না জানলে modern UI build করা কঠিন!

---

# 🧩 1. Basic Selectors

### ✅ Element Selector
```css
p { color: red; }
```

### ✅ Class Selector
```css
.box { background: blue; }
```

### ✅ ID Selector
```css
#hero { padding: 20px; }
```

### ✅ Universal Selector
```css
* { margin: 0; }
```

### ✅ Group Selector
```css
h1, h2, h3 { font-weight: bold; }
```

---

# 🧲 2. Attribute Selectors

### Contains value
```css
a[href*="google"] { color: red; }
```

### Starts with
```css
a[href^="https"] { font-weight: bold; }
```

### Ends with
```css
img[src$=".png"] { border: 2px solid; }
```

### Exact match
```css
input[type="text"] { background: yellow; }
```

---

# 🎚️ 3. Multiple Classes
```css
.card.big { font-size: 20px; }
```

---

# 🧬 4. Descendant Selector
```css
.container p { color: green; }
```

---

# 🧱 5. Child Selector (`>`)
Only direct child
```css
ul > li { list-style: none; }
```

---

# 🧊 6. Adjacent Sibling (`+`)
Immediately next element
```css
h2 + p { margin-top: 10px; }
```

---

# 🧲 7. General Sibling (`~`)
```css
h2 ~ p { color: gray; }
```

---

# 🔥 8. Pseudo-class Selectors

### Hover
```css
button:hover { background: black; }
```

### Active
```css
a:active { color: red; }
```

### Focus
```css
input:focus { border-color: blue; }
```

### Checked
```css
input:checked { scale: 1.2; }
```

### Disabled
```css
button:disabled { opacity: .5; }
```

### First-child
```css
p:first-child { color: orange; }
```

### Last-child
```css
p:last-child { color: purple; }
```

### nth-child()
```css
li:nth-child(3) { color: red; }
```

Even/Odd:
```css
tr:nth-child(even) { background: #eee; }
```

---

# 🌱 Structural Pseudo-classes

### only-child
```css
p:only-child { color: green; }
```

### not()
```css
p:not(.big) { font-size: 14px; }
```

---

# 🧩 Pseudo-element Selector

### First letter
```css
p::first-letter { font-size: 3rem; }
```

### First line
```css
p::first-line { font-weight: bold; }
```

### Before
```css
h1::before {
  content: "🔥 ";
}
```

### After
```css
h1::after {
  content: " ✅";
}
```

### Selection
```css
::selection { background: yellow; }
```

---

# 🔐 Form State Selectors

### required
```css
input:required { border: 2px solid red; }
```

### valid
```css
input:valid { border-color: green; }
```

### invalid
```css
input:invalid { border-color: red; }
```

---

# 📌 Language Selector
```css
:lang(en) { font-style: italic; }
```

---

# 🧠 UI State Selectors

```css
:fullscreen {}
:focus-visible {}
:focus-within {}
```

---

# 🧲 Attribute Presence Selector
```css
[target] { color: blue; }
```

---

# 🧨 Advanced Attribute Operators

### Space separated match
```css
[class~="title"] { color: tomato; }
```

### Hyphen match
```css
[class|="btn"] { padding: 10px; }
```

---

# 📦 Combinators Summary

| Symbol | Meaning |
|--------|---------|
| space  | descendant |
| >      | direct child |
| +      | adjacent sibling |
| ~      | general sibling |

---

# 🧠 Specificity Rules (Very Important)

| Type | Score |
|------|-------|
| Inline style | 1000 |
| ID | 100 |
| Class/Attribute/Pseudo-class | 10 |
| Element/Pseudo-element | 1 |
| Universal | 0 |

✅ More score = More priority

---

# 🔥 Specificity Example
```css
#id > .box p { color: red; }
```

Score = 100 + 10 + 1 = 111

---

# 🧮 Practical Specificity Trick
Avoid using too many IDs  
Prefer class-based styling

---

# 🎯 Selector Levels (Pro)

1. Target element by attribute
2. Filter with state
3. Style parts with pseudo-element

Example:
```css
input[type="email"]:focus::placeholder { color: red; }
```

---

# 🧩 Chaining Selectors
```css
input.big.error:focus { border-color: red; }
```

---

# 💣 Performance Tips
✅ Short selectors
✅ Avoid universal selectors `*`
✅ Use class instead of ID for components

---

# 🚫 Anti-patterns
❌ Over-specificity
```css
div.container ul li a span {}
```

---

# 🧠 Super Useful Modern Selectors

### :is()
Simplify long selector lists

```css
:is(h1, h2, h3){ margin: 0; }
```

### :where()
Zero specificity

```css
:where(.card .title){ color: blue; }
```

### :has() (Parent selector!) ✅
```css
.card:has(img){ border: 2px solid green; }
```

✅ Reacts based on children

---

# 🔥 Parent Style Based on Child
```css
.form:has(.error){
  border: 2px solid red;
}
```

Game changer!

---

# 🧬 nth-of-type()
```css
p:nth-of-type(2){ color: blue; }
```

---

# 🎚️ Even/Odd row zebra
```css
tr:nth-child(even){ background: #eee; }
```

---

# 🎁 Common UI Patterns

### Button hover
```css
button:hover{ scale: 1.1; }
```

### Input focus visible
```css
input:focus-visible{ outline: 2px solid blue; }
```

---

# 🧠 Interview Questions

❓ Specificity ranking?  
❓ Difference `:nth-child` vs `:nth-of-type`?  
❓ Use cases of `:has()`?  
❓ Difference between `:before` and `::before`?  
❓ How to target parent based on child?  

---

# 🏁 Conclusion
CSS Selectors mastery = Clean, scalable, professional code.  
Selectors না জানলে responsive component-driven UI build অসম্ভব!

Happy Styling 🎨🚀
