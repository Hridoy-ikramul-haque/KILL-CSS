
# CSS Flexbox — Complete Notes (A to Z)

## ✅ Introduction
Flexbox (Flexible Box Layout) is a one‑dimensional layout system used to arrange items in a row or column with intelligent space distribution. It helps align, order, and distribute space among items inside a container.

---

## 📌 Why Flexbox?
- Easy centering
- Handles spacing automatically
- Great for alignment
- Responsive-friendly
- Reduces manual margin hacks

---

## 🔧 Flex Container Properties
These properties are applied to the parent container.

### 1. display
```css
display: flex;
display: inline-flex;
```

### 2. flex-direction
Defines the main axis direction:
```css
flex-direction: row;        /* default */
flex-direction: row-reverse;
flex-direction: column;
flex-direction: column-reverse;
```

### 3. flex-wrap
Allows items to wrap onto multiple lines:
```css
flex-wrap: nowrap;    /* default */
flex-wrap: wrap;
flex-wrap: wrap-reverse;
```

### 4. flex-flow (direction + wrap)
Shorthand:
```css
flex-flow: row wrap;
```

### 5. justify-content (Main-axis alignment)
```css
justify-content: flex-start;
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

### 6. align-items (Cross-axis alignment)
```css
align-items: stretch; /* default */
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;
```

### 7. align-content (multiple line spacing)
Works when wrapping is enabled:
```css
align-content: stretch;
align-content: flex-start;
align-content: flex-end;
align-content: center;
align-content: space-between;
align-content: space-around;
```

---

## 🎯 Flex Item Properties
These properties apply to children inside a flex container.

### 1. order
Controls item ordering:
```css
order: 0; /* default */
```

Lower number = first

### 2. flex-grow
Controls available-space growth:
```css
flex-grow: 1;
```

### 3. flex-shrink
Controls shrinking when space is tight:
```css
flex-shrink: 1; /* default */
```

### 4. flex-basis
Initial size:
```css
flex-basis: 200px;
```

### 5. flex (shorthand)
```css
flex: grow shrink basis;
flex: 1 1 100px;
```

### 6. align-self
Overrides align-items:
```css
align-self: flex-start;
align-self: flex-end;
align-self: center;
align-self: stretch;
```

---

## 📐 Axes
Main axis ← flex-direction
Cross axis ↕ perpendicular to main axis

- `row` → Main axis horizontal
- `column` → Main axis vertical

---

## 🧍 Center Anything with Flexbox
```css
display: flex;
justify-content: center;
align-items: center;
```

---

## 📝 Common Layout Example
```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
```

---

## 📦 Flexbox vs Grid
| Flexbox | Grid |
|--------|------|
| 1D Layout | 2D Layout |
| row or column | rows + columns |
| Content-based | Layout-based |

Use Both Together 😎

---

## ⚡ Responsive Navbar Example
```css
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

---

## 🔥 Cheatsheet
```css
display: flex;
flex-direction: row | column;
flex-wrap: wrap | nowrap;
justify-content: center | space-between;
align-items: center | stretch;
align-content: space-around;
flex: 1 1 auto;
order: 2;
align-self: flex-end;
```

---

## ❌ Common Mistakes
- Using margin hacks to center
- Confusing align-items vs align-content
- Forgetting wrap while using align-content

---

## ✅ Best Practices
- Avoid fixed width
- Use flex: 1 for equal growth
- Combine with media queries for responsiveness

---

## 🧠 Flex Shorthand Deep Dive
```css
flex: grow shrink basis;
flex: 0 0 auto;
flex: 1;      /* grow */
flex: 1 0;    /* grow, no shrink */
flex: 1 1 200px;
```

---

## 👌 Equal Width Children
```css
.child {
  flex: 1;
}
```

---

## 🎉 Conclusion
Flexbox is **powerful**, **simple**, and **perfect** for modern responsive layouts. Master it → and your UI alignment problems disappear.

Happy coding 👨‍💻🔥

---

## 🧩 Flexbox Visual Diagram (Mindmap)

Main Axis  ← flex-direction →
Cross Axis ↕ perpendicular

Container:
  ├─ display
  ├─ flex-direction
  ├─ flex-wrap
  ├─ justify-content
  ├─ align-items
  └─ align-content

Items:
  ├─ order
  ├─ flex-grow
  ├─ flex-shrink
  ├─ flex-basis
  └─ align-self

Responsive:
  └─ flex-flow

---

## 🧪 10 Practical Flex Layouts

### 1️⃣ Center Box
```css
display: flex;
justify-content: center;
align-items: center;
```

### 2️⃣ Horizontal Menu
```css
display: flex;
gap: 1rem;
```

### 3️⃣ Space Between Items
```css
display: flex;
justify-content: space-between;
```

### 4️⃣ Wrapping Grid-like Layout
```css
display: flex;
flex-wrap: wrap;
gap: 10px;
```

### 5️⃣ Sidebar + Content
```css
display: flex;
```

### 6️⃣ Equal-Width Columns
```css
.child {
  flex: 1;
}
```

### 7️⃣ Auto-Growing Search Bar
```css
input {
  flex: 1;
}
```

### 8️⃣ Vertical Align Center
```css
align-items: center;
```

### 9️⃣ Reverse Items
```css
flex-direction: row-reverse;
```

### 🔟 Mobile Stack Layout
```css
@media(max-width: 600px){
  flex-direction: column;
}
```

---

## ❓ Flexbox Interview Questions

1. What is the main axis vs cross axis?
2. Difference between justify-content vs align-items?
3. When to use flex-grow?
4. How does flex-basis work?
5. Why flexbox is responsive-friendly?
6. What align-content does?
7. Difference between flex and inline-flex?
8. Explain flex: 1
9. How to center using flexbox?
10. Common mistakes using flexbox?

---

## 🥊 Flexbox vs Grid Comparison Table

| Feature | Flexbox | Grid |
|--------|--------|------|
| Axes | 1D | 2D |
| Best For | Components | Layouts |
| Direction | Row/Column | Rows/Columns |
| Area Naming | ❌ | ✅ |
| Alignment | Excellent | Good |

---

## 🏁 Mini Assignments

### ✅ Exercise 1
Create a horizontally centered nav menu using flexbox.

### ✅ Exercise 2
Build a card layout that wraps on small screens.

### ✅ Exercise 3
Make two columns: sidebar (30%) and content (70%).

### ✅ Exercise 4
Create a button group spread evenly.

### ✅ Exercise 5
Center a login box vertically + horizontally.

---

Happy practicing! 🚀🔥
