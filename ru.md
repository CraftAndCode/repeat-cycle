# Повторяющий цикл

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
Привет! Сегодня мы научимся включать в наши программы элементы циклов.  
  
Некоторые примеры в этом уроке будут использовать светодиодную ленту. Подключи её так, как показано на схеме.
![](https://raw.githubusercontent.com/CraftAndCode/neopixel-extension/master/strip.png)

## Step 1 @showDialog
### Что такое цикл?
Циклом называется часть программы, которая выполняет некоторые команды не один, а несколько раз.

В предыдущих программах мы уже использовали цикл ``||basic.постоянно||``, который выполняет программу снова и снова. Для некоторых задач этого может быть достаточно, но часто нам может понадобиться повторить программу или её часть заданное количество раз. Здесь нам на помощь приходят блоки циклов из вкладки ``||loops.циклы||``.

## Step 2 @showDialog
### Цикл "повторить"
Цикл ``||loops.повторить||`` выполняет команды внутри столько раз, сколько указано в шапке блока.

```block
for (let index = 0; index < 4; index++) {
}
```

## Step 3 @showHint
### Цикл "повторить"
Давай попробуем этот блок в действии. Собери программу по образцу и попробуй менять число в шапке блока ``||loops.повторить||``. Как это изменение влияет на работу программы?
```blocks
for (let index = 0; index < 4; index++) {
    basic.showIcon(IconNames.Heart)
    basic.clearScreen()
    basic.pause(500)
}
```
## Step 3.5 @showDialog
### Цикл "повторить"
Среди программистов мастерством считается умение написать программу, используя минимальное количество команд. Давай посмотрим, как им это удаётся?
  
Эта программа заполняет светодиодную ленту случайными цветами:
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
  
А вот программа, которая выполняет точно то же самое, но использует цикл для экономии памяти устройства:
```blocks
let strip = neopixel.create(DigitalPin.P0, 10, NeoPixelMode.RGB)
for (let index = 0; index < 10; index++) {
    strip.setPixelColor(0, randint(neopixel.colors(NeoPixelColors.Black), neopixel.colors(NeoPixelColors.White)))
    strip.rotate(1)
    }
strip.show()
```


## Step 4 @showHint
### Цикл "повторить"
Мы предлагаем тебе собрать по очереди обе программы и загрузить их в Micro:bit, чтобы убедиться, что они работают одинаково. 
   
Какую программу легче составить?
```hint
Программа без цикла:
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
  
Программа с циклом:
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
### Пример 1: Чередующиеся цвета
Этот пример показывает, как с помощью повторяющего цикла заполнить ленту двумя чередующимися цветами
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
### Пример 2: Постепенное заполнение
В этом примере цикл с повторением используется, чтобы постепенно заполнять ленту то зелёным, то синим цветом.
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
### Теперь твой черёд!
Дополни программу из предыдущего примера так, чтобы на ленте постепенным заполнением сменялось три разных цвета.
## Step 8 @showDialog
### Ответы: Теперь твой черёд!
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
Мы научились использовать цикл с повторением! В следующих уроках мы узнаем, как нам могут помочь цикл с условием и цикл со счётчиком.
