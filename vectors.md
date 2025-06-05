# Vectors 

```template
scene.onOverlapTile(SpriteKind.Player, myTiles.tile2, function (sprite, location) {
    game.over(false)
})
scene.onOverlapTile(SpriteKind.Player, myTiles.tile4, function (sprite, location) {
    game.over(true)
})
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.vy = -200
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    otherSprite.destroy()
    if (sprite.bottom < otherSprite.y) {
        sprite.vy = -100
    } else {
        info.changeLifeBy(-1)
    }
})
let myEnemy: Sprite = null
let mySprite: Sprite = null
scene.setBackgroundColor(11)
mySprite = sprites.create(img`
    3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
    3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 1 1 1 3 3 3 1 3 3 3 1 3
    3 1 3 3 1 3 3 1 3 1 1 3 3 3 1 3
    3 1 3 3 1 3 3 1 3 3 1 3 3 3 1 3
    3 1 3 3 1 1 1 3 3 3 1 3 3 3 1 3
    3 1 3 3 1 3 3 3 3 3 1 3 3 3 1 3
    3 1 3 3 1 3 3 3 3 1 1 1 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 3 3 3 3 3 3 3 3 3 3 3 3 1 3
    3 1 1 1 1 1 1 1 1 1 1 1 1 1 1 3
    3 3 3 3 3 3 3 3 3 3 3 3 3 3 3 3
    `, SpriteKind.Player)
mySprite.ay = 500
controller.moveSprite(mySprite, 100, 0)
scene.cameraFollowSprite(mySprite)
info.setLife(3)
tiles.setTilemap(tilemap`level`)
tiles.placeOnRandomTile(mySprite, myTiles.tile3)
for (let value of tiles.getTilesByType(myTiles.tile5)) {
    myEnemy = sprites.create(img`
        a a a a a a a a a a a a a a a a
        a b b b b b b b b b b b b b b a
        a b a a a a a a a a a a a a b a
        a b a a b b a a a a b b a a b a
        a b a a a a b a a b a a a a b a
        a b a a a a a a a a a a a a b a
        a b a a a b a a a a b a a a b a
        a b a a a b a a a a b a a a b a
        a b a a a a a a a a a a a a b a
        a b a a a a a a a a a a a a b a
        a b a a a b b b b b b a a a b a
        a b a a b a a a a a a b a a b a
        a b a a a a a a a a a a a a b a
        a b a a a a a a a a a a a a b a
        a b b b b b b b b b b b b b b a
        a a a a a a a a a a a a a a a a
        `, SpriteKind.Enemy)
    tiles.placeOnTile(myEnemy, value)
    myEnemy.follow(mySprite, 30)
}


```

## Welcome 
This is text