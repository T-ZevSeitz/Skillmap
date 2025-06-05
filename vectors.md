# Vectors

```template
sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {
    info.changeLifeBy(-1)
    sprites.destroy(otherSprite)
})
let enemyAttack: Sprite = null
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
info.setLife(3)
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
controller.A.onEvent(ControllerButtonEvent.Pressed, function() {
    enemyAttack = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . 4 4 . . . . . . . 
        . . . . . . 4 5 5 4 . . . . . . 
        . . . . . . 2 5 5 2 . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Projectile)
    enemyAttack.setPosition(myEnemy.x, myEnemy.y)
    enemyAttack.follow(mySprite, 0)

})


```
```ghost
    myEnemy.follow(mySprite)
    function doSomething() {
    dX = target.x - self.x
    dx = Math.sqrt(0)
    pause(100)
}
```
## Step 1

When making a game, its often needed to get one object to move towards another. The best way of doing this is with Vectors which MakeCode does not come with, so we need to make our own.

In this example we have a Player and an Enemy. We want the Enemy to shoot at the Player and the Player to dodge.
To test the enemy shoots whenever the we press "A"
## Step 2

To start off with lets look at the tools MakeCode comes with, being the ``||sprites:follow ||`` function alrea in our A code.

Try out changing the speed 0 to 100. See how this makes a Projectile move towards the Player every time you press space.

## Dodging
Unfortnently we cannot dodge this Projectile as it keeps following the Player. 

We need something that starts to follow but then keeps moving in one direction, and for this we need to use Vectors.

## Vectors
A Vector is a quanitity with a magnitude and direction.
