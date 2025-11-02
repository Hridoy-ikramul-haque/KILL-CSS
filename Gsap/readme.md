
# ⚡ GSAP (GreenSock Animation Platform) — Pro Guide A→Z (Bangla)

## ✅ Introduction
GSAP হলো world-class JavaScript animation library:
- Smooth
- GPU accelerated
- Cross-browser perfect
- Timeline control
- Scroll-based animation (ScrollTrigger)

Framer Motion এর আগেও GSAP ছিল industry standard।

---

## 🚀 Why GSAP?
✅ Fastest JS animation engine  
✅ Precise timeline control  
✅ Lag-free performance  
✅ Massive plugin ecosystem  
✅ Motion sequencing সহজ করে  

---

## 📦 How to install

### CDN:
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
```

### NPM:
```bash
npm i gsap
```

---

## 🧱 Basic structure

```js
gsap.to(".box", {
  x: 200,
  duration: 1,
  ease: "power2.out",
});
```

- `.to()` → From current to new values
- `.from()` → From starting values
- `.fromTo()` → Define both

---

## 🔥 .to() Example
```js
gsap.to(".card", {
  y: -50,
  opacity: 1,
  duration: 0.6,
});
```

---

## 🔥 .from() Example
```js
gsap.from(".heading", {
  y: 40,
  opacity: 0,
  duration: 0.7,
});
```

---

## 🔥 .fromTo() Example
```js
gsap.fromTo(".img",
  { opacity: 0, scale: 0.7 },
  { opacity: 1, scale: 1, duration: 1 }
);
```

---

## 🎨 Easing (Realistic Motion)
Built-in easings:
```
power1.out
power2.inOut
back.out(1.7)
elastic.out(1, 0.4)
bounce.out
```

Example:
```js
ease: "back.out(1.5)"
```

---

## 🎬 Timeline Basics
Multiple animation sequence control:

```js
const tl = gsap.timeline();

tl.to(".box", { x: 100 })
  .to(".box", { y: 50 })
  .to(".box", { scale: 1.5 });
```

✅ Runs step-by-step

---

## 🧠 Why timeline?
- Chain animation
- Overlap control
- Pause/play/resume
- Reverse animation possible

---

## ⏱️ Overlap timing

```js
tl.to(".a", { x: 100 })
  .to(".b", { y: 100 }, "-=0.3");
```

`"-=0.3"` → 0.3 second overlap

---

## 🎯 Stagger (multiple items)

```js
gsap.from(".item", {
  opacity: 0,
  y: 20,
  stagger: 0.2,
});
```

Each item animate with gap.

---

## 🔄 Reverse animation
```js
tl.reverse();
```

---

## 🛑 Stop/Pause/Restart
```js
tl.pause();
tl.resume();
tl.restart();
```

---

## 🏁 Callback events
```js
onStart: () => console.log("Started"),
onComplete: () => console.log("Done!")
```

---

## 🎥 Scrub Animation (scroll-based)
ScrollTrigger plugin required.

```js
gsap.to(".box", {
  x: 500,
  scrollTrigger: {
    trigger: ".section",
    scrub: true
  }
});
```

Scroll progress অনুযায়ী animation চলবে।

---

## 📌 Pin element (parallax section)
```js
scrollTrigger: {
  trigger: ".hero",
  pin: true
}
```

---

## 📏 Scroll position start/end
```js
start: "top 80%",
end: "top 10%",
```

---

## 🎨 Markers (debug)
```js
markers: true
```

---

## 🧭 ScrollTrigger full example

```js
gsap.from(".text", {
  y: 60,
  opacity: 0,
  duration: 1,
  scrollTrigger: {
    trigger: ".text",
    start: "top 80%",
    end: "top 30%",
    scrub: 1,
    markers: true
  }
});
```

---

## 🧲 Pin + scrub combined

```js
gsap.to(".panel", {
  x: "-100%",
  scrollTrigger: {
    trigger: ".wrapper",
    pin: true,
    scrub: 2
  }
});
```

---

## 🎯 Performance Tips
✅ animate transform, opacity  
❌ avoid width, height, top, left  

---

## 📌 Utility: set()
Without animation jump-set:

```js
gsap.set(".box", { opacity: 0 });
```

---

## 🎛 CSS Variables animate

```js
gsap.to(":root", {
  "--color": "#0f0",
  duration: 1,
});
```

---

## 📦 Plugins list (pro level)

✅ ScrollTrigger  
✅ MotionPathPlugin  
✅ TextPlugin  
✅ Flip  
✅ Observer  
✅ Inertia  

---

## 🧬 Motion Path
SVG path follow করানো যায়।

```js
gsap.to(".ball", {
  duration: 3,
  repeat: -1,
  motionPath: "#curve"
});
```

---

## 🔁 Repeat + yoyo

```js
repeat: -1, // infinite
yoyo: true,
```

---

## ⚡ QuickTo (ultra fast)

```js
const move = gsap.quickTo(".box", "x", { duration: 0.3 });
move(200);
```

Great for mousemove!

---

## 🐁 Mouse follow effect

```js
window.addEventListener("mousemove", e => {
  gsap.to(".cursor", { x: e.clientX, y: e.clientY });
});
```

---

## 🧠 Smooth ScrollTrigger Setup Advice
Use CSS:
```
html, body { overflow-x: hidden; }
```

---

## 📐 Responsive GSAP

```js
ScrollTrigger.matchMedia({
  "(max-width: 768px)": function() {
    // mobile animation
  }
});
```

---

## 👀 Observer Plugin (scroll, touch, wheel)

```js
Observer.create({
  target: window,
  onDown: () => tl.play(),
  onUp: () => tl.reverse()
});
```

---

## 🧩 FLIP Plugin (Layout transition animations)
Perfect for filtering UI cards.

---

## 🚫 Common Mistakes

❌ Animate left/top property  
✅ Animate x/y transform

❌ Using duration on scrub  
✅ Scrub controls time

---

## ✅ GSAP Best Practices

✔ Always timeline for sequences  
✔ Keep durations small (0.5–1.2s)  
✔ Use stagger for delight  
✔ Combine with scrollTrigger  

---

## 🧠 Interview questions
- Why GSAP faster than CSS animation?
- Difference timeline vs independent animation?
- What is scrub in ScrollTrigger?
- Why transform preferred over top/left?

---

## 💻 Basic project layout

```html
<section class="hero"></section>
<section class="about"></section>
<section class="services"></section>
```

Animations on scroll for each.

---

## 🧠 Real-world use cases

✅ Landing page hero reveal  
✅ Card hover micro animations  
✅ Scroll parallax text  
✅ Logo intro animation  
✅ SVG path drawing  
✅ Testimonials slider motion  

---

## 🧯 Debug checklist

- turn on markers
- check trigger position
- overflow hidden issue?
- transform origin set?

---

## 🏁 Conclusion
GSAP = Pro-grade web motion engine:

✅ Smooth  
✅ Precise control  
✅ Scroll-based  
✅ Plugin rich  
✅ Industry used (Apple, Google, Nike)

Master this → Your UI becomes 💎 premium.

Happy Animating 🚀


---

# 🧩 Extra Practical GSAP Examples (Included)

## ✅ Fade-in on load
```js
gsap.from(".hero", {
  opacity: 0,
  duration: 1.2,
});
```

## ✅ Slide-up cards stagger
```js
gsap.from(".card", {
  y: 40,
  opacity: 0,
  duration: 0.8,
  stagger: 0.15,
});
```

## ✅ Button hover scale
```js
document.querySelector("button").addEventListener("mouseenter", () => {
  gsap.to("button", {
    scale: 1.1,
    duration: 0.2,
  });
});
```

## ✅ Scroll-based fade & move
```js
gsap.to(".section-title", {
  y: -30,
  opacity: 1,
  scrollTrigger: {
    trigger: ".section-title",
    start: "top 80%",
    scrub: true,
  }
});
```

## ✅ Horizontal scroll panels
```js
gsap.to(".panels", {
  x: "-200%",
  scrollTrigger: {
    trigger: ".panels-wrapper",
    scrub: 1,
    pin: true,
    start: "top top",
    end: "+=2000"
  }
});
```

## ✅ Text reveal (clip-path)
```js
gsap.from(".reveal", {
  clipPath: "inset(0 100% 0 0)",
  duration: 1.1,
  ease: "power4.out"
});
```

## ✅ SVG stroke drawing
```js
gsap.from(".path", {
  strokeDasharray: 1000,
  strokeDashoffset: 1000,
  duration: 2
});
```

## ✅ Floating element loop
```js
gsap.to(".float", {
  y: -10,
  repeat: -1,
  yoyo: true,
  duration: 1.4,
});
```

## ✅ Loader timeline sequence
```js
const tl = gsap.timeline();
tl.to(".bar", { width: "80%", duration: 1 })
  .to(".loader", { opacity: 0 })
  .to(".app", { opacity: 1 });
```

## ✅ Mouse parallax depth
```js
window.addEventListener("mousemove", (e) => {
  gsap.to(".layer", { x: e.clientX / 10, y: e.clientY / 10 });
});
```

---

# 🎁 Micro Interaction Examples

## Button tap bounce
```js
gsap.to(".btn", {
  scale: 0.9,
  duration: 0.1,
  yoyo: true,
  repeat: 1
});
```

## Card hover tilt
```js
gsap.to(".card", {
  rotateY: 10,
  duration: 0.3,
  ease: "power2.out"
});
```

---

# ✅ All examples included successfully.
