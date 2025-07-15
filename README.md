# Stopwatch
# ⏱️ Stopwatch App

A simple and elegant **Stopwatch** built with **HTML**, **CSS**, and **JavaScript**.  
Track hours, minutes, and seconds with Start, Pause, and Reset controls.

---

## 🎯 Features

- Displays time in `HH:MM:SS` format
- Start the stopwatch and count up every second
- Pause the stopwatch at any time
- Reset to zero instantly
- Clean, user-friendly UI with smooth button effects

---

## 🧠 What I Learned

1. **Time Management with JavaScript**  
   - Using `setInterval()` and `clearInterval()` to control timer updates.

2. **DOM Manipulation**  
   - Updating the displayed time dynamically.

3. **Conditional Logic**  
   - Handling seconds to minutes and minutes to hours conversion.

4. **CSS Styling**  
   - Flexbox centering, button styling, and smooth hover transitions.

---

## 🚀 How to Use

1. Open `index.html` in your browser.
2. Click **Start** to begin the timer.
3. Use **Pause** to stop the timer temporarily.
4. Click **Reset** to clear the timer back to zero.

---

## 🖥️ Code Snippet

```js
let [hours, minutes, seconds] = [0, 0, 0];
let timer = null;

function updateDisplay() {
  const display = document.getElementById("display");
  let h = hours < 10 ? "0" + hours : hours;
  let m = minutes < 10 ? "0" + minutes : minutes;
  let s = seconds < 10 ? "0" + seconds : seconds;
  display.innerText = `${h}:${m}:${s}`;
}

function stopwatch() {
  seconds++;
  if (seconds === 60) {
    seconds = 0;
    minutes++;
  }
  if (minutes === 60) {
    minutes = 0;
    hours++;
  }
  updateDisplay();
}

function start() {
  if (timer !== null) return;
  timer = setInterval(stopwatch, 1000);
}

function pause() {
  clearInterval(timer);
  timer = null;
}

function reset() {
  clearInterval(timer);
  timer = null;
  [hours, minutes, seconds] = [0, 0, 0];
  updateDisplay();
}
## 🚀 Live Demo

Check out the live demo here:  
[Stopwatch App Live Demo](https://muskanpandey2103.github.io/stopwatch-app/)
