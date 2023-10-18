<div id="ball" style="
  z-index: 5;
  position: absolute;
  left: 0px;
  top: 0px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: mediumpurple;"></div>

<script>
var velocityX = 200; // Horizontal velocity
var velocityY = 200; // Vertical velocity 
var positionX = 0;
var positionY = 0;
var ball = document.getElementById('ball');
var reverseX = false;
var reverseY = false;


function moveBall() {
  if (!reverseX) {
    positionX += velocityX;
    if (positionX >= 1000 - ball.clientWidth) {
      reverseX = true;
    }
  } else {
    positionX -= velocityX;
    if (positionX <= 0) {
      reverseX = false;
    }
  }

  if (!reverseY) {
    positionY += velocityY;
    if (positionY >= 500 - ball.clientHeight) { 
      reverseY = true;
    }
  } else {
    positionY -= velocityY;
    if (positionY <= 0) {
      reverseY = false;
    }
  }

  ball.style.left = positionX + 'px';
  ball.style.top = positionY + 'px';
}

setInterval(moveBall, 100);
</script>