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

![Banner Image](github-readme-contents/example-1-output.gif)
