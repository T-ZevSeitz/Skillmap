# Vectors 
```template
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . f f f f f f . . . . . 
    . . . f f e e e e f 2 f . . . . 
    . . f f e e e e f 2 2 2 f . . . 
    . . f e e e f f e e e e f . . . 
    . . f f f f e e 2 2 2 2 e f . . 
    . . f e 2 2 2 f f f f e 2 f . . 
    . f f f f f f f e e e f f f . . 
    . f f e 4 4 e b f 4 4 e e f . . 
    . f e e 4 d 4 1 f d d e f f . . 
    . . f e e e 4 d d d d f d d f . 
    . . . . f e e 4 e e e f b b f . 
    . . . . f 2 2 2 4 d d e b b f . 
    . . . f f 4 4 4 e d d e b f . . 
    . . . f f f f f f e e f f . . . 
    . . . . f f . . . f f f . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite, 0, 100)
mySprite.setStayInScreen(true)
mySprite.left = 0
let myEnemy = sprites.create(img`
    . . . . . . f f f f . . . . . . 
    . . . . f f 1 1 1 1 f f . . . . 
    . . . f b 1 1 1 1 1 1 b f . . . 
    . . . f 1 1 1 1 1 1 1 d f . . . 
    . . f d 1 1 1 1 1 1 1 d d f . . 
    . . f d 1 1 1 1 1 1 d d d f . . 
    . . f d 1 1 1 d d d d d d f . . 
    . . f d 1 d f b d d d d b f . . 
    . . f b d d f c d b b b c f . . 
    . . . f 1 1 1 1 1 b b c f . . . 
    . . . f 1 b 1 f f f f f . . . . 
    . . . f b f c 1 1 1 b f . . . . 
    . . . . f f 1 b 1 b f f . . . . 
    . . . . . f b f b f f f . f . . 
    . . . . . . f f f f f f f f . . 
    . . . . . . . . f f f f f . . . 
    `, SpriteKind.Enemy)
myEnemy.right = 160

```

## Welcome @unplugged

Now let's take a look at the [__*sidescrolling*__](#scrolld "games that are viewed from the side, with most of the action happening horizontally") 
[__*platformer*__](#plat "games that rely on jump and run as their main mechanic").  

This kind of game peeks in on the action from the side, using "jump" and "run"
as the main mechanic.  

By the time you finish this set of tutorials, you should know all you need 
to make a fun and engaging arcade game worth sharing.

![Our first platformer](/static/skillmaps/platformer/platformer1.gif "Look what we're about to learn today!")