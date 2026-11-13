
# Space Invaders

## Step 1: Create your spaceship

Let's build a Space Invaders game!

First, we need a spaceship.

1. Open the **Sprites** category.
2. Drag `set mySprite to sprite of kind Player` into `on start`.
3. Click the grey image box.
4. Draw your own spaceship.

```blocks
let mySprite = sprites.create(img`
    . . . 8 . . .
    . . 8 8 8 . .
    . 8 8 8 8 8 .
    8 8 8 8 8 8 8
`, SpriteKind.Player)
```

Click **Next** when your spaceship is ready.

## Step 2: Move your spaceship

Now let's make the spaceship move.

1. Open the **Controller** category.
2. Find `move mySprite with buttons`.
3. Place it inside `on start`, underneath your spaceship.

```blocks
controller.moveSprite(mySprite)
```

**Test:** Can you move your spaceship using the arrow keys?

## Step 3: Keep your spaceship on screen

We don't want our spaceship disappearing off the edge!

1. Open the **Sprites** category.
2. Find `set mySprite stay in screen ON`.
3. Add it to `on start`.
4. Make sure it is set to **ON**.

```blocks
mySprite.setStayInScreen(true)
```

**Test:** Try moving your spaceship to the edge of the screen.

## Step 4: Fire a laser

Our spaceship needs a weapon!

1. Open the **Controller** category.
2. Drag out `on A button pressed`.
3. Open the **Sprites** category.
4. Find `set projectile to projectile from mySprite`.
5. Place it inside the button event.
6. Set `vx` to `0` and `vy` to `-100`.
7. Draw a small laser image.

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let projectile = sprites.createProjectileFromSprite(img`
        2
        2
        2
    `, mySprite, 0, -100)
})
```

**Test:** Press A. Does your laser travel upwards?

## Step 5: Add an enemy

Let's give our spaceship something to shoot at.

1. Open the **Sprites** category.
2. Add another `set mySprite to sprite of kind Player` block inside `on start`.
3. Change the variable name to `enemy`.
4. Change the sprite kind from **Player** to **Enemy**.
5. Draw an alien.
6. Use `set enemy position to x 80 y 20` to place it near the top.

```blocks
let enemy = sprites.create(img`
    . 7 . 7 .
    7 7 7 7 7
    7 . 7 . 7
    7 7 7 7 7
`, SpriteKind.Enemy)
enemy.setPosition(80, 20)
```

**Test:** Can you see your enemy at the top of the screen?

## Tutorial Complete!

Well done! You've started building Space Invaders.

Your game now has:

- A spaceship you can control.
- A laser that fires when you press A.
- An enemy spaceship.

Next time, we'll make enemies move and add collisions so you can destroy them!

    
