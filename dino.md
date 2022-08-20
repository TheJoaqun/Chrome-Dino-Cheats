# Chrome Dino Cheats (Full Source And Javascript Friendly Tutorial)

Starting First Open Developers Tools By Using ShortCut `Ctrl+Shift+I (Windows)` or `Opt+Shift+I(Mac)`

### Dev Tools Console

- Make Sure You Are In A Tab Named `Console` In There You Can Run Any Script But Be Aware Of Maldicius Scripts.
- We Are Going To Run Scripts In Console Tab To Hack Into It (Dino Crhome Is Very Easy To Cheat In Game)

### Change Speed

This Script Can Edit Dino Speed (Speed Limit: None ~ Default: 10)

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

This Script Can Edit Dino JumpPower (JumpPower Limit: None ~ Default: 10)

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
