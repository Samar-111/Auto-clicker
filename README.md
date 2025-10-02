AutoClicker for Website (JavaScript)

This is a simple, browser-side autoclicker that repeatedly triggers clicks on an element inside your own website. It can be useful for demos, testing, or playful interactions with elements like buttons.

Features

Start/Stop buttons to control the autoclicker.

Adjustable interval (default: 300 ms).

Works with any element on your page (just set its ID).

Features

Start/Stop buttons to control the autoclicker.

Adjustable interval (default: 300 ms).

Works with any element on your page (just set its ID).

Pure JavaScript — no external libraries required.

Installation

Add the following HTML snippet somewhere in your page (for demo purposes):
<div id="target">
  <button id="clickMeBtn">Click me (target)</button>
</div>

<button id="startBtn">Start AutoClick</button>
<button id="stopBtn">Stop</button>
<p id="status">Stopped</p>
Add the JavaScript code before your closing </body> tag:
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

  /
  document.getElementById("clickMeBtn").addEventListener("click", () => {
    console.log("Target button clicked at " + new Date().toLocaleTimeString());
  });
</script>

