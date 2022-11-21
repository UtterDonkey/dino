# How to Make RTX Chrome Dino Game

## Step 1 - Choose Assets

Choose your assets and store them in your folder with your HTML file. You will need a dinosaur (`dinosaur-walk.gif`), a cactus (`cactus.png`) and ground (`ground.jpg`).

## Step 2 - Write Basic HTML Layout

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daniel's Dino DJ</title>
    <style>
        body{
            margin: 0px;
        }
    </style>
</head>
<body>
    <h1></h1>
    <img id="dino" src="./dinosaur-walk.gif">
    <img id="ground" class="ground" src="./ground.jpg">
    <img id="ground2" class="ground" src="./ground.jpg">
    <div id="things">

    </div>
    <script>
        const dino = document.querySelector('#dino');
        const ground = document.querySelector('#ground');
        const ground2 = document.querySelector('#ground2');
        let Y = 0;
        let Yvelocity = 0;
        let X = 0;
    </script>
</body>
</html>
```

## Step 3 - Create Scrolling Background

Add This to your CSS:

```css

        .ground{
            position: fixed;
            object-fit: cover;
            height: auto;
            width: 100%;
        }
        #ground2{
            transform: scaleX(-1);
        }
```

And add this to you JavaScript:

```js

function tick(){
            dino.style.translate = `0% calc( -100% - ${Y}vh)`;
            ground.style.left = ((X-100)%200)+100 + 'vw';
            ground2.style.left = (X%200)+100 + 'vw';
            X = X-0.2;
            setTimeout(tick, 0);
        }
        tick();
```

