# CSS Animation Snippets

## Example 0

####  HTML CODE

```html

<!DOCTYPE html>
<html >
  <head>
    <meta charset="UTF-8">
    <title>Playing a CSS animation on hover</title>
    <link href="styles.css" type="text/css" media="all" rel="Stylesheet"/>

  </head>

  <body>

    <link href='http://fonts.googleapis.com/css?family=Bree+Serif' rel='stylesheet' type='text/css'>

<div class="wrap">
  <div class="sticker"></div>
  <div class="msg">new!</div>
</div>

  </body>
</html>

```

####  CSS CODE

```css
body {padding:6em; background:#fcfcfc;}

.wrap {width:200px; margin:auto;  z-index:1;}

.msg {
  color: whitesmoke;
  text-align:center;
  font-family: 'Bree Serif', Courier, monospaced;
  font-size:3.5em;
  width:200px;
  position:absolute;
  margin:55px 0 0 2px;
  pointer-events: none;
}

.sticker {
  width:200px;
  height:200px;
  position:absolute;
  background: url(sticker.png) top center no-repeat;
  animation:spin 10s linear infinite;
  animation-play-state:paused;/*It is pasused*/
}

    .sticker:hover {/*Running*/


        animation-play-state:running;
    }


@keyframes spin {

    0%{transform:rotate(0turn);}
    100%{transform:rotate(1turn);}
    /*1turn means it will completly rotate once.*/

}

```

#### Output

![Banner Image](github-readme-contents/example-0-output.gif)

## Example 1

####  HTML CODE

```html

<html>
	<head>
		<title>Animation Basics</title>		
		<link rel="stylesheet" href="styles.css" media="all" />
	</head>
	<body>

	<div class="wrapper">
		<img src="tall_robot.svg" width="150" alt="tall robot" class="robot" />
	</div>

	</body>
</html>

```

####  CSS CODE

```css
body {
	background-image: url('background.png');
	background-size: cover;
	background-position: 0px -250px;
}

.wrapper {
	margin: 20em auto 2em auto;
	width:80%;
	position:relative;
}

.robot {

  animation-name:slide;
  animation-duration:3s;
  animation-timing-function:ease-in;
  animation-iteration-count:1;/*infinite will not stop*/
  animation-delay:1s;
  animation-fill-mode:forwards;/*The aniamtion-fill-mode is useful to decide how to finish the animation*/
                               /*backwords and both*/
}

@keyframes slide{

	from{transform:translate(0px);}
	to{transform:translate(900px);}


}

```

#### Output

![Banner Image](github-readme-contents/example-1-output.gif)

## Example 2

####  HTML CODE

```html
<html>
	<head>
		<title>animation-fill-mode</title>
		<link rel="stylesheet" href="styles.css" media="all" />
	</head>

	<body>		
		<img class="ball" src="ball.png" alt="ball"width="111" height="111" />
	</body>

</html>
```

####  CSS CODE

```css

body {margin: 4em 10%; background:#493F5B;}

 .ball {
	animation-name: move-left-right;
	animation-duration: 2s;
	animation-timing-function: ease-in;
	animation-iteration-count: 1;
 	animation-delay:1s;
    animation-fill-mode:both;
}

@keyframes move-left-right {
	0% {transform: translateX(100px) rotate(0turn);}
	20% {transform: translateX(-10px) rotate(-0.5turn);}
	100% {transform:translateX(450px) rotate(2turn);}			
}
```

#### Output

![Banner Image](github-readme-contents/example-2-output.gif)


## Example 3

####  HTML CODE

```html
<html>
	<head>
		<title>Animation Basics</title>		
		<link rel="stylesheet" href="styles.css" media="all" />
	</head>
	<body>

	<div class="wrapper">
		<img src="tall_robot.svg" width="150" alt="tall robot" class="robot" />
	</div>

	</body>
</html>

```

####  CSS CODE

```css
body {
	background-image: url('background.png');
	background-size: cover;
	background-position: 0px -250px;
}

.wrapper {
	margin: 20em auto 2em auto;
	width:80%;
	position:relative;
}

.robot {
	animation-name: slide;
	animation-duration: 2s;
	animation-timing-function: ease-in;
	animation-iteration-count: 1;
	animation-fill-mode:forwards;
    animation-direction:reverse;/*This will run the animation reversly*/
}

@keyframes slide {
	from {transform: translateX(0);}
	to {transform: translateX(900px);}
}
```

#### Output

![Banner Image](github-readme-contents/example-3-output.gif)

## Example 4

####  HTML CODE

```html
<html>
	<head>
		<title>Animation Basics</title>		
		<link rel="stylesheet" href="styles.css" media="all" />
	</head>
	<body>

	<div class="wrapper">
		<img src="tall_robot.svg" width="150" alt="tall robot" class="robot" />
	</div>

	</body>
</html>
```

####  CSS CODE

```css

body {
	background-image: url('background.png');
	background-size: cover;
	background-position: 0px -250px;
}

.wrapper {
	margin: 20em auto 2em auto;
	width:80%;
	position:relative;
}

.robot {
	animation-name: slide;
	animation-duration: 2s;
	animation-timing-function: ease-in;
	animation-iteration-count: 2;/*We should make to 2*/
	animation-fill-mode:forwards;
    animation-direction:alternate;/*This will move the element in both*/
}

@keyframes slide {
	from {transform: translateX(0);}
	to {transform: translateX(900px);}
}
```

#### Output

![Banner Image](github-readme-contents/example-4-output.gif)

## Example 5

####  HTML CODE

```html
<html>
	<head>
		<title>Animation Basics</title>		
		<link rel="stylesheet" href="styles.css" media="all" />
	</head>
	<body>

	<div class="wrapper">
		<img src="tall_robot.svg" width="150" alt="tall robot" class="robot" />
	</div>

	</body>
</html>
```

####  CSS CODE

```css
body {
	background-image: url('background.png');
	background-size: cover;
	background-position: 0px -250px;
}

.wrapper {
	margin: 20em auto 2em auto;
	width:80%;
	position:relative;
}

.robot {
	animation-name: slide;
	animation-duration: 2s;
	animation-timing-function: ease-in;
	animation-iteration-count: 2;/*We should make to 2*/
	animation-fill-mode:forwards;
    animation-direction:alternate-reverse;/*This will move the element from reverse to start*/
}

@keyframes slide {
	from {transform: translateX(0);}
	to {transform: translateX(900px);}
}
```

#### Output

![Banner Image](github-readme-contents/example-5-output.gif)

## Example 6

####  HTML CODE

```html
<html>
	<head>
		<title>Animation Basics</title>		
		<link rel="stylesheet" href="styles.css" media="all" />
	</head>
	<body>

	<div class="wrapper">
		<img src="tall_robot.svg" width="150" alt="tall robot" class="robot" />
	</div>

	</body>
</html>
```

####  CSS CODE

```css
body {
	background-image: url('background.png');
	background-size: cover;
	background-position: 0px -250px;
}

.wrapper {
	margin: 20em auto 2em auto;
	width:80%;
	position:relative;
}

.robot {
	animation-name: slide;
	animation-duration: 3s;
	animation-timing-function: cubic-bezier(.41,.07,.62,.91) ;
	animation-fill-mode:forwards;
	animation-direction: alternate;
	animation-iteration-count: 4;
}

@keyframes slide {
	0%{transform: translateX(0);}
	20% {transform:translateX(200px);}
	35% {transform:translateX(0);}
	90% {transform: translateX(980px);}
	100% {transform: translateX(900px);}
}
```

#### Output

![Banner Image](github-readme-contents/example-6-output.gif)

## Example 7

####  HTML CODE

```html
<!DOCTYPE html>
<html>
<head>
	<title>Clouds</title>
	<link rel="stylesheet" href="styles.css" media="all" />

</head>
<body>

<div class="sky">
	<div class="cloud fcloud01"></div>
	<div class="cloud fcloud02"></div>
</div>

</body>
</html>
```

####  CSS CODE

```css
body {
  background:#678bb3;
  padding:0;
  margin:0;
}

.sky {
  width:100%;
  height:1000px;
  background: transparent url(img/sky.jpg) top left no-repeat;
  background-size: 100% 100%;
  margin:auto;
  position:relative;
}

.cloud {
  width: 250px;
  height:200px;
  position:absolute;
  background:transparent url(img/front_cloud.png) 0 0 no-repeat;
}

.fcloud01 {
  top:100px;
  z-index:100;

      animation:drift 25s linear infinite;
      /*Animation name,duration,type of timing function , iteration-count*/
  }

.fcloud02 {
  top:240px;
  z-index: 200;

      animation:drift 45s  linear infinite;
        /*Animation name,duration,delay,type of timing function , iteration-count*/
}

@keyframes drift {

  from{transform:translateX(-255px);}
  to{transform:translateX(1350px);}

}
```

#### Output

![Banner Image](github-readme-contents/example-7-output.gif)
