# Google Colab Auto-Connect: Prevent Session Disconnections | Code Script

When using [Google Colab](https://colab.research.google.com) for extended sessions, it's important to prevent disconnections that can lead to data and variable loss. Avoid this issue by running the following code in your browser's console (accessed by pressing <button>Ctrl</button> + <button>Shift</button> + <button>I</button>).

```javascript

let isPaused = false;

function ClickConnect() {
  if (!isPaused) {
    console.log("Working");
    document.querySelector("colab-toolbar-button").click();
  }
}

let intervalId = setInterval(ClickConnect, 60000);

// Method to pause execution
function pauseExecution() {
  isPaused = true;
  console.log("Execution paused");
}

// Method to resume execution
function resumeExecution() {
  isPaused = false;
  console.log("Execution resumed");
}

```

You can call pauseExecution() to pause script execution and call resumeExecution() to resume it whenever you want.
