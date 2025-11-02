
# 🎬 CSS Animation & Transition — A to Z Complete Notes (Bangla)

## ✅ Introduction
CSS Animation & Transition ব্যবহার করা হয় element-এর movement, visual effects, hover feedback,
smooth UI interaction এবং micro‑interaction তৈরি করার জন্য।  
Modern UI‑তে এগুলো **must‑know**।

---

# ⚡ Part 1 — CSS Transition

## 🎯 Transition কী?
এক state থেকে অন্য state‑এ পরিবর্তন হওয়াকে smooth করে।  

Example:
Hover করলে button color ধীরে change হয়।

---

## 🧩 Syntax
```css
transition: property duration timing-function delay;
```

### Example:
```css
box {
  transition: all 0.4s ease;
}
```

---

## 🔸 1. transition-property
কোন property transition হবে?
```css
transition-property: width;
```

Common properties:
- width
- height
- color
- background
- opacity
- transform

---

## 🔸 2. transition-duration
কত সময়ে পরিবর্তন হবে?
```css
transition-duration: 0.6s;
```

---

## 🔸 3. transition-timing-function
Animation speed control করে

### Common values:
- ease
- ease-in
- ease-out
- ease-in-out
- linear

```css
transition-timing-function: ease-in-out;
```

---

## 🔸 4. transition-delay
Animation start শুরু হবে কিছুক্ষণ পরে
```css
transition-delay: 0.3s;
```

---

## ✅ Shorthand
```css
transition: background 0.5s ease 0.2s;
```

---

## 🔥 Hover Example
```css
.box {
  width: 100px;
  background: red;
  transition: width 0.5s;
}

.box:hover {
  width: 200px;
}
```

---

## 💡 Multiple Properties
```css
transition: width 0.5s, background 0.5s;
```

---

# 🎬 Part 2 — CSS Animation

## 🎯 Animation কী?
Element‑কে continuous অথবা repeated motion দেয়।  
Transition শুধু state change হলে কাজ করে  
Animation auto run করতে পারে।

---

## 🧩 Keyframe
এখানে animation‑এর steps define করা হয়

```css
@keyframes example {
  from { opacity: 0; }
  to   { opacity: 1; }
}
```

---

## 🔥 Set to element
```css
.box {
  animation-name: example;
  animation-duration: 2s;
}
```

---

# 📌 Animation Properties

## 1️⃣ animation-name
কোন keyframe drive করবে?

## 2️⃣ animation-duration
কত সময় animation চলবে?

## 3️⃣ animation-timing-function
speed control

## 4️⃣ animation-delay
start হওয়ার আগে delay

## 5️⃣ animation-iteration-count
কতবার repeat হবে?

```css
animation-iteration-count: infinite;
```

## 6️⃣ animation-direction
Reverse movement
- normal
- reverse
- alternate
- alternate-reverse

```css
animation-direction: alternate;
```

## 7️⃣ animation-fill-mode
Animation শেষ হলে final state ধরে রাখে

Values:
- forwards
- backwards
- both

```css
animation-fill-mode: forwards;
```

## 8️⃣ animation-play-state
Pause/Resume

```css
animation-play-state: paused;
```

---

## 🧠 Shorthand
```css
animation: example 2s ease-in-out 0.4s infinite alternate forwards;
```

---

# 🎉 Fade In Animation
```css
@keyframes fade {
  from { opacity: 0; }
  to   { opacity: 1; }
}

.box {
  animation: fade 1s;
}
```

---

# ⚠️ Transition vs Animation (Difference)

| Feature | Transition | Animation |
|---------|------------|-----------|
| Trigger | Required | Auto run |
| Keyframe | ❌ | ✅ |
| Loop | ❌ | ✅ |
| Complex motion | ❌ | ✅ |

---

# 🔥 Transform + Animation combo
```css
@keyframes spin {
  to { transform: rotate(360deg); }
}

.loader {
  animation: spin 1s linear infinite;
}
```

---

# 🕹️ Hover Animation
```css
@keyframes jump {
  0% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0); }
}

.box:hover {
  animation: jump 0.4s;
}
```

---

# 🧠 Animation Timing Functions

| Name | Behavior |
|------|----------|
| ease | slow → fast |
| ease-in | slow start |
| ease-out | slow end |
| linear | constant |
| steps(n) | instant jumps |

---

# ⏱️ Steps Animation (Sprite)
```css
animation-timing-function: steps(4);
```

---

# 🎯 animation-fill-mode (Important)

| Value | Effect |
|-------|--------|
| none | no final frame |
| forwards | keep last frame |
| backwards | apply first frame before animation |
| both | combine both |

---

# 🎥 animation-direction

| Value | Behavior |
|-------|----------|
| normal | normal |
| reverse | backwards |
| alternate | forward → reverse |
| alternate-reverse | reverse → forward |

---

# 🪄 Animation Pause on Hover
```css
.box:hover {
  animation-play-state: paused;
}
```

---

# 📐 Performance Best Practice

✅ Use `transform` & `opacity`
❌ Avoid width / height animation (laggy)

---

# 💡 Animation Delay Trick
Animation run হবে ভিন্ন সময়ে

```css
.box:nth-child(2){
  animation-delay: 0.2s;
}
```

---

# 😎 Real‑World Use Cases
✅ Button hover effect
✅ Loading spinners
✅ Notification pop-in
✅ Menu slide
✅ Toast animation
✅ Hero banner reveal

---

# 🧪 Mini Assignment
✅ Fade‑in cards
✅ Pulse button
✅ Floating icon
✅ Expandable menu
✅ Typing loader

---

# 🗂️ Cheatsheet

```css
transition:
  property duration timing-function delay;
  
animation:
  name duration timing-function delay iteration-count direction fill-mode;
```

---

# 🧠 Interview Questions

❓ Difference between animation & transition?  
❓ What is animation-fill-mode?  
❓ Infinite animation usage?  
❓ Which properties are GPU‑friendly?  
❓ Keyframe % meaning?  

---

# 🏁 Conclusion
Animation & transition UI‑কে smooth, interactive, modern করে।  
User experience অনেক‑গুণ improve হয়।  
Master these → UI Rock Star 👑🔥

Happy Coding! 🚀


---

# 🧲 CSS Transform — Complete Guide

## ✅ What is transform?
Element-এর shape/position/rotation/scale/skew পরিবর্তন করে—layout affect না করে!  
(GPU accelerated → smooth performance)

---

## 🔸 translate (move)
Element কে X/Y axis এ সরায়

```css
transform: translate(20px, 30px);
```

### Only X:
```css
transform: translateX(50px);
```

### Only Y:
```css
transform: translateY(-20px);
```

✅ Use case: Button hover push, slide animation

---

## 🔸 scale (zoom)
Element বড়/ছোট করে

```css
transform: scale(1.3);
```
### X / Y scale:
```css
transform: scaleX(2);
transform: scaleY(0.5);
```

✅ Use: Hover zoom effect

---

## 🔸 rotate (spin)
Element ঘোরানো

```css
transform: rotate(45deg);
```

✅ Use: Loader, icon turning

---

## 🔸 skew (tilt)
Element কে ঢালু করা

```css
transform: skew(20deg);
```

---

## 🎯 Multiple Transform Together
```css
transform: translateX(20px) scale(1.3) rotate(10deg);
```

⚠️ Order matters!

---

## 🛑 transform-origin
Rotate/scale কোথা থেকে শুরু হবে

```css
transform-origin: center;
transform-origin: top left;
```

---

## 🧲 3D Transforms

### rotateX (tilt towards you)
```css
transform: rotateX(40deg);
```

### rotateY (card flip horizontal)
```css
transform: rotateY(180deg);
```

### translateZ (push out)
```css
transform: translateZ(50px);
```

✅ Requires `perspective`

---

## 🔮 Perspective
3D effect depth দেয়

```css
.container {
  perspective: 600px;
}
```

---

# 🎥 Transform with Transition Example

```css
.box {
  transition: transform 0.3s;
}

.box:hover {
  transform: translateY(-10px) scale(1.1);
}
```

✅ Smooth hover UI

---

# 🔥 Transform with Animation Example

```css
@keyframes jump {
  50% { transform: translateY(-20px); }
}

.ball {
  animation: jump 0.5s infinite;
}
```

---

# 🧠 Performance Tip
✅ Always animate: transform, opacity  
❌ Avoid: width, margin, top/left

(GPU optimization)

---

