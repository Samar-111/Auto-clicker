# AutoClicker for Website (JavaScript)

A simple client-side autoclicker that repeatedly triggers clicks on an element inside your own website.  


⚠️ **Note:** This works only inside your page. It cannot and should not be used to click on other websites or bypass browser restrictions.

---

 ✨ Features
- Start/Stop buttons to control the autoclicker  
- Adjustable interval (default: 300 ms)  
- Works with any HTML element (just set its ID)  
- Pure JavaScript, no external libraries  

---

## 🚀 Installation

1. Add this snippet to your HTML page (for demo):

html
<div id="target">
  <button id="clickMeBtn">Click me (target)</button>
</div>

<button id="startBtn">Start AutoClick</button>
<button id="stopBtn">Stop</button>
<p id="status">Stopped</p>

2.Add the JavaScript before your closing </body> tag:
```javascript
<script>
  let intervalId = null;

  function startAutoClick() {
    if (intervalId) return;
    const el = document.getElementById("clickMeBtn");
    intervalId = setInterval(() => {
      el.click();
    }, 300);
    document.getElementById("status").textContent = "Running...";
  }

  function stopAutoClick() {
    if (intervalId) {
      clearInterval(intervalId);
      intervalId = null;
    }
    document.getElementById("status").textContent = "Stopped";
  }

  document.getElementById("startBtn").addEventListener("click", startAutoClick);
  document.getElementById("stopBtn").addEventListener("click", stopAutoClick);

   document.getElementById("clickMeBtn").addEventListener("click", () => {
    console.log("Target button clicked at " + new Date().toLocaleTimeString());
  });
</script>

