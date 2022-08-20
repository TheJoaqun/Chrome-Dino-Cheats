# Chrome Dino Cheats (Full Source And Javascript Friendly Tutorial)

Starting First Open Developers Tools By Using ShortCut `Ctrl+Shift+I (Windows)` or `Opt+Shift+I(Mac)`

## Index

[Auto Bot](https://github.com/thejoaqun/chrome-dino-cheats/blob/master/dino.md#auto-dino-bot)

- Make Sure You Are In A Tab Named `Console` In There You Can Run Any Script But Be Aware Of Maldicius Scripts.
- We Are Going To Run Scripts In Console Tab To Hack Into It (Dino Crhome Is Very Easy To Cheat In Game)

### Change Speed

This Script Can Edit Dino Speed (Speed Limit: None ~ Default: 6)

> First Example

```js
const newSpeed = 100; // This Variable Define Speed And Then We Call It In Line 2
Runner.instance_.setSpeed(newSpeed); // This Function Makes Dino To Change Speed, The Part Of Code ".setSpeed(speed)" speed is the number value of speed defined in the first line.
```

> Second Example

```js
Runner.instance_.setSpeed(100);
```

### Change JumpPower

This Script Can Edit Dino JumpPower (JumpPower Limit: None ~ Default: 0.6)

> First Example

```js
const newJumpPower = 10; // This Variable Define Speed And Then We Call It In Line 2
Runner.instance_.tRex.setJumpVelocity(newJumpPower); // This Function Makes Dino To Change Speed, The Part Of Code ".setSpeed(speed)" speed is the number value of speed defined in the first line.
```

> Second Example

```js
Runner.instance_.tRex.setJumpVelocity(10);
```

### Change Gravity

This Script Can Edit Dino Gravity (Gravity Limit: None ~ Default: 0.6)

> First Example

```js
const newGravity = 0.1; // This Variable Define Speed And Then We Call It In Line 2
Runner.instance_.tRex.config.GRAVITY = newGravity; // This Function Makes Dino To Change Speed, The Part Of Code ".setSpeed(speed)" speed is the number value of speed defined in the first line.
```

> Second Example

```js
Runner.instance_.tRex.config.GRAVITY = 0.1;
```

### Obstacle Remover

Remove Dino Obstacle

> Manual Pressing 'E'

```js
b = Runner.instance_.clearCanvas;
window.addEventListener("keydown", checkKeyPressed, false); // Listen "E" Key

function checkKeyPressed(l) {
  if (l.keyCode == "69") {
    // If "e" Key Pressed Then
    drawline();
  }
}
function drawline() {
  if (Runner.instance_.horizon.obstacles.length > 0) {
    // Check If Has Obstacle
    Runner.instance_.clearCanvas = function () {};
    /* Visual */
    Runner.instance_.canvasCtx.beginPath();
    Runner.instance_.canvasCtx.moveTo(
      Runner.instance_.tRex.xPos + 23,
      Runner.instance_.tRex.yPos + 20
    );
    Runner.instance_.canvasCtx.lineTo(
      Runner.instance_.horizon.obstacles[0].xPos + 10,
      Runner.instance_.horizon.obstacles[0].yPos + 10
    );
    Runner.instance_.canvasCtx.stroke();
    setTimeout(function () {
      Runner.instance_.clearCanvas = b;
    }, 50);
    Runner.instance_.horizon.removeFirstObstacle(); // remove obstacle
  }
}
```

> AutoMatic (Lower Interval Speed Better)

```js
setInterval(function () {
  b = Runner.instance_.clearCanvas;
  if (Runner.instance_.horizon.obstacles.length > 0) {
    // Check If Has Obstacle
    console.log(
      `Removed: ` + Runner.instance_.horizon.obstacles.length + ` Obstacle`
    ); // Debuger
    Runner.instance_.clearCanvas = function () {};
    /* Visual */
    Runner.instance_.canvasCtx.beginPath();
    Runner.instance_.canvasCtx.moveTo(
      Runner.instance_.tRex.xPos + 23,
      Runner.instance_.tRex.yPos + 20
    );
    Runner.instance_.canvasCtx.lineTo(
      Runner.instance_.horizon.obstacles[0].xPos + 10,
      Runner.instance_.horizon.obstacles[0].yPos + 10
    );
    Runner.instance_.canvasCtx.stroke();
    setTimeout(function () {
      Runner.instance_.clearCanvas = b;
    }, 50);
    Runner.instance_.horizon.removeFirstObstacle(); // remove obstacle
  }
}, 0.5 * 1000); // Repeater Seconds * Miliseconds (Only Change Seconds Do Not Edit Miliseconds Interval & Timeout CalCultes In MiliSeconds)
```

### No Obstacle Game (Static)

Stop Character But The Games Its Works Normally

> Enable

```js
Runner.instance_.playingIntro = true;
```

> Disable

```js
Runner.instance_.playingIntro = false;
```

### Auto Dino Bot

```js
function keyDown(keyCode) {
  var event = document.createEvent("KeyboardEvent");
  Object.defineProperty(event, "keyCode", {
    get: function parseKeyDown() {
      return this.keyCodeVal;
    },
  });
  if (event.initKeyboardEvent) {
    event.initKeyboardEvent(
      "keydown",
      true,
      true,
      document.defaultView,
      keyCode,
      keyCode,
      "",
      "",
      false,
      ""
    );
  } else {
    event.initKeyEvent(
      "keydown",
      true,
      true,
      document.defaultView,
      false,
      false,
      false,
      false,
      keyCode,
      0
    );
  }
  event.keyCodeVal = keyCode;
  document.body.dispatchEvent(event);
}
function keyUp(keyCode) {
  var event = document.createEvent("KeyboardEvent");
  Object.defineProperty(event, "keyCode", {
    get: function get() {
      return this.keyCodeVal;
    },
  });
  if (event.initKeyboardEvent) {
    event.initKeyboardEvent(
      "keyup",
      true,
      true,
      document.defaultView,
      keyCode,
      keyCode,
      "",
      "",
      false,
      ""
    );
  } else {
    event.initKeyEvent(
      "keyup",
      true,
      true,
      document.defaultView,
      false,
      false,
      false,
      false,
      keyCode,
      0
    );
  }
  event.keyCodeVal = keyCode;
  document.body.dispatchEvent(event);
}
setInterval(function () {
  if (Runner.instance_.horizon.obstacles.length > 0) {
    if (
      Runner.instance_.horizon.obstacles[0].xPos <
        25 * Runner.instance_.currentSpeed -
          Runner.instance_.horizon.obstacles[0].width / 2 &&
      Runner.instance_.horizon.obstacles[0].yPos > 75
    ) {
      keyUp(40);
      keyDown(38);
    }
    if (
      Runner.instance_.horizon.obstacles[0].xPos <
        30 * Runner.instance_.currentSpeed -
          Runner.instance_.horizon.obstacles[0].width / 2 &&
      Runner.instance_.horizon.obstacles[0].yPos <= 75
    ) {
      keyDown(40);
    }
  }
}, 5);
```
