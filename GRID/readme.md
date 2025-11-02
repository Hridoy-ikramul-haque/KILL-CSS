
# CSS Grid – Full Guide (Bangla README Notes)

## 🔰 Introduction
CSS Grid হলো ওয়েব লেআউট সিস্টেম যা 2D (rows + columns) এ কনটেন্ট সাজাতে ব্যবহৃত হয়।
Flexbox = একদিকে ভালো, Grid = দুই দিকেই সমানভাবে কাজ করে।

## ✅ Basic Setup
```css
.container {
  display: grid;
}
```

## 📌 Grid Anatomy Diagram
```
| 1 |----- Track -----| 2 |----- Track -----| 3 |
  ← Column Line →         ← Column Line →
```

```
┌───────────── Container ─────────────┐
│  Item Item Item                     │
│  Item Item Item                     │
└─────────────────────────────────────┘
```

## 🧩 Core Grid Properties

### ✅ grid-template-columns
Column সংখ্যা ও সাইজ নির্ধারণ:
```css
grid-template-columns: 200px 200px 200px;
grid-template-columns: 1fr 2fr 1fr;
grid-template-columns: repeat(3, 1fr);
```

### ✅ grid-template-rows
```css
grid-template-rows: 100px 200px;
```

### ✅ gap
```css
gap: 20px;
row-gap: 10px;
column-gap: 20px;
```

### ✅ minmax()
```css
grid-template-columns: minmax(200px, 1fr);
```

### ✅ repeat()
```css
repeat(4, 1fr)
```

### ✅ auto-fill / auto-fit
Responsive layout:
```css
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

### ✅ grid-column
```css
.item { grid-column: span 2; }
.item { grid-column: 1 / 4; }
```

### ✅ grid-row
```css
.item { grid-row: span 2; }
```

### ✅ justify-items
```css
justify-items: center;
```

### ✅ align-items
```css
align-items: center;
```

### ✅ place-items
```css
place-items: center;
```

### ✅ justify-content
```css
justify-content: center;
```

### ✅ align-content
```css
align-content: center;
```

### ✅ grid-auto-rows
```css
grid-auto-rows: 150px;
```

### ✅ grid-auto-flow
```css
grid-auto-flow: row;
grid-auto-flow: column;
grid-auto-flow: dense;
```

## 🎨 Grid Template Areas Example
```css
grid-template-areas:
  "header header"
  "sidebar content"
  "footer footer";
```

## 🧠 Line-Based Placement
```css
grid-column: 1 / 3;
grid-row: 2 / 4;
```

## 🔁 Nested Grid
```css
.child { display: grid; }
```

## 📦 Implicit vs Explicit Grid
Explicit:
```css
grid-template-columns: repeat(3, 1fr);
```
Implicit:
```css
grid-auto-rows: 100px;
```

## 📏 Units Summary
| Unit | Explanation |
|------|-------------|
| fr | free space |
| auto | content-based |
| % | responsive |
| px | fixed |
| min-content | smallest possible |
| max-content | largest possible |

## ✅ Complete Example
```css
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
  place-items: center;
}
```

## 🔨 Common Patterns
Center content:
```css
place-items: center;
```

Masonry:
```css
grid-auto-rows: 10px;
```

## 🎯 Best Practices
- Use `fr`
- Use auto-fit + minmax()
- Use template areas for complex layout

## ⚠️ Avoid
- fixed px everywhere
- unnecessary nested grids

## ✅ Use Cases
- Dashboard
- Gallery
- Portfolio
- Admin UI
- Pricing table

## 💡 Grid vs Flex
| Feature | Flex | Grid |
|---------|------|------|
| 1D layout | ✅ | 🟡 |
| 2D layout | ❌ | ✅ |
| Complex UI | 🟡 | ✅ |
| Simplicity | ✅ | 🟡 |

## 🧪 Practice Tasks
1. 3 column responsive card grid
2. First item span 2 columns
3. Sidebar + content + footer
4. Masonry auto rows
5. Center item both axis

## ✅ Assignment Solutions

### Assignment 1
2D layout using grid-template-areas ✔

### Assignment 2
3x3 square grid ✔ (aspect-ratio)

### Assignment 3
Responsive card grid via auto-fit ✔

### Assignment 4
Stretch item top to bottom using `grid-row: 1 / -1;`

### Assignment 5
Masonry layout using `grid-auto-rows` & `grid-row: span`

## 🚀 Bonus
Backward line numbers supported:
```css
grid-column: 1 / -1;
```

## 🧩 Mini Cheatsheet
```
display: grid
grid-template-columns
grid-template-rows
grid-template-areas
grid-column
grid-row
gap
repeat()
minmax()
auto-fit
auto-fill
place-items
justify-items
align-items
```





<!-- cheatsheet -->
🎯 CSS GRID CHEATSHEET (Bangla Version)

✅ Grid শুরু করতে
.container {
  display: grid;
}

✅ Column সেট করতে
grid-template-columns: 100px 100px 100px;

✅ Repeat ব্যবহার
grid-template-columns: repeat(3, 100px);

✅ Fraction Unit (Most Used)
grid-template-columns: 1fr 2fr 1fr;

✅ Rows সেট করতে
grid-template-rows: 100px 200px;

✅ Gap (Spacing)
gap: 20px;
row-gap: 20px;
column-gap: 10px;

✅ Responsive Auto-fit / Auto-fill
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));

✅ minmax()
grid-template-columns: minmax(100px, 300px);

✅ Grid Auto Flow
grid-auto-flow: row;
grid-auto-flow: column;
grid-auto-flow: dense;

✅ Grid Item Span
.item {
  grid-column: span 2;
  grid-row: span 3;
}

✅ Line based placement
.item {
  grid-column: 1 / 4;
  grid-row: 2 / 3;
}

✅ Full Stretch
grid-row: 1 / -1;

✅ Named template area (Powerful)
Parent:
grid-template-areas:
  "header header"
  "sidebar main"
  "footer footer";

Children:
.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main { grid-area: main; }
.footer { grid-area: footer; }

✅ Implicit Grid (Extra items)
grid-auto-rows: 100px;
grid-auto-columns: 200px;

✅ Alignment Properties (Container)
justify-items: center; /* x-axis */
align-items: center;   /* y-axis */
place-items: center;   /* shortcut */

justify-content: space-between;
align-content: space-between;

✅ Alignment (Single Item)
justify-self: center;
align-self: center;

✅ Center everything
place-items: center;

✅ Simple 3 Column Layout
grid-template-columns: repeat(3, 1fr);

✅ Responsive Card Layout
grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
gap: 20px;

✅ Masonry Style
grid-auto-rows: 10px;

✅ Order Items
.item {
  order: 2;
}

✅ Nested Grid
.child {
  display: grid;
}

✅ Grid Shorthand
grid: auto / repeat(3, 1fr);

✅ Quick inspect tip
Chrome DevTools → Layout → Grid Overlay ON

📌 Rules (Pocket Guide)
Flex = 1D layout
Grid = 2D layout

Use fr more, px less
auto-fit + minmax = responsive magic

❌ Avoid
Too many fixed px
Ignoring gap
Not using chrome overlay

🔥 Bonus Comparison
Navbar → Flex
Card Layout → Grid
Complex Layout → Grid
Responsive Columns → Grid

🏁 Most Used Snippet
.container {
  display: grid;
  gap: 20px;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  place-items: center;
}




## ✅ Conclusion
CSS Grid is modern, powerful & responsive layouting system.
