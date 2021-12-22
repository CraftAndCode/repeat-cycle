# Repeat loop

```package
core
radio
microphone
neopixel=github:microsoft/pxt-neopixel
```

```template
basic.forever(function () {
})
```

```blocks
basic.forever(function () {
strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
for (let index = 0; index < 4; index++) {
    basic.showIcon(IconNames.Heart)
}
})
```

## Step 0 @showDialog
Hello! Today we're going to learn how to include loops in our programs.
  
Some of the examples in this tutorial will use LED strip lights. Connect the strip as shown in the diagram.
![](https://raw.githubusercontent.com/CraftAndCode/neopixel-extension/master/strip.png)

## Step 1 @showDialog
### What is a loop?

A loop is a part of a program that executes specific commands not once but several times.

In earlier programs, we used the ``||basic.forever||`` loop which runs a program over and over. For some tasks, this may be sufficient, but sometimes we may need to repeat a program or part of it a given number of times. This is where loop blocks from the ``||loops.loops||`` folder come to our rescue.

## Step 2 @showDialog
### Repeat loop
A ``||loops.repeat||`` block executes the commands inside as many times as indicated in the block header.

```block
for (let index = 0; index < 4; index++) {
}
```

## Step 3 @showHint
### Repeat loop
Let's see this block in action. Build the program following the example and try changing the number in the header of the ``||loops.repeat||`` block. How does this change affect the operation of the program?
```block
for (let index = 0; index < 4; index++) {
    basic.showIcon(IconNames.Heart)
    basic.clearScreen()
    basic.pause(500)
}
```
## Step 3.5 @showDialog
### Repeat loop
Among programmers, the ability to write a program using a minimum number of instructions counts as mastery. Let's see how they do it!
  
This program fills the LED strip with random colors:
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
strip.setPixelColor(0, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(1, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(2, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(3, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(4, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(5, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(6, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(7, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(8, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(9, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.show()
```
  
And here is a program that does exactly the same thing, but uses a loop to save device memory:
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
for (let index = 0; index < 10; index++) {
    strip.setPixelColor(0, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
    strip.rotate(1)
    }
strip.show()
```

## Step 4 @showHint
### Repeat loop
We suggest you build both programs separately and then download them to the Micro:bit to make sure they work the same way.
   
Which program is easier to write?
```hint
A program with no loops:
```
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
strip.setPixelColor(0, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(1, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(2, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(3, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(4, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(5, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(6, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(7, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(8, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.setPixelColor(9, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
strip.show()
```
```hint
  
A program with a loop:
```
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
for (let index = 0; index < 10; index++) {
    strip.setPixelColor(0, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
    strip.rotate(1)
}
strip.show()
```
## Step 5 @showHint
### Example 1: Alternating Colors
This example shows how to use a repeat loop to fill a LED strip with two alternating colors.
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
for (let index = 0; index < 10; index++) {
    strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
    strip.setPixelColor(1, neopixel.colors(NeoPixelColors.Yellow))
    strip.rotate(2)
}
strip.show()
```
## Step 6 @showHint
### Example 2: Gradual filling
In this example, a repeat loop is used to gradually fill the strip with green and blue alternately.
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
basic.forever(function () {
    for (let index = 0; index < 10; index++) {
        strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(100)
        strip.rotate(1)
    }
    for (let index = 0; index < 10; index++) {
        strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Blue))
        strip.show()
        basic.pause(100)
        strip.rotate(1)
    }
})

```

## Step 7
### Now it's your turn!
Complete the program in the previous example so that the strip gradually fills in three different colors.
## Step 8 @showDialog
### Answers: Now it's your turn!
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
basic.forever(function () {
    for (let index = 0; index < 10; index++) {
        strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Green))
        strip.show()
        basic.pause(100)
        strip.rotate(1)
    }
    for (let index = 0; index < 10; index++) {
        strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Blue))
        strip.show()
        basic.pause(100)
        strip.rotate(1)
    }
    for (let index = 0; index < 10; index++) {
        strip.setPixelColor(0, neopixel.colors(NeoPixelColors.Red))
        strip.show()
        basic.pause(100)
        strip.rotate(1)
    }
})
```
## Step 9
We've learned how to use a repeat loop! In the next lessons, we will learn how a conditional loop and a counter loop can help us.

