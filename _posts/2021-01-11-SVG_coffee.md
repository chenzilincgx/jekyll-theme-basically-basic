---
layout: page
title: SVG也能平移？变形？
excerpt_separator: "<!--more-->"
tags:
        - SVG制作
---
    

<!--more-->
以下为SVG动画：
<style>
.body {
  margin: 0;
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Open Sans", "Lucida Sans Unicode", "Lucida Grande", sans-serif;
  font-size: 14px;
}

.background {
  position: relative;
  background: linear-gradient(to bottom, #3a92af 0%, #2e7086 100%);
  border-radius: 5px;
  box-shadow: 0 5px 15px 0 rgba(0, 0, 0, 0.25);
  width: 400px;
  height: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.circle,
.triangle,
.octagon {
  position: absolute;
}

.circle,
.circleRing {
  width: 100px;
  height: 100px;
  background-color: white;
  border-radius: 50%;
  animation: circle 5s ease-in-out infinite;
}

.triangle,
.octagon {
  fill: white;
  width: 150px;
  height: 100px;
  top: 150px;
  left: 150px;
  margin: auto;
  transform: scale(0);
  transform-origin: 50px 50px;
}

.triangle {
  animation: triangle 5s ease-in-out infinite;
}

.octagon {
  animation: octagon 5s ease-in-out infinite;
  transform: rotate(22.5deg);
}

.circleRing {
  border: 3px solid white;
  border-radius: 50%;
  background-color: transparent;
  animation: circleRing 5s ease-in-out infinite;
}

.octagonSparkles {
  position: absolute;
  width: 200px;
  height: 200px;
  top: 100px;
  left: 100px;
  animation: octagonSparkles 5s ease-in-out infinite;

  .sparkle {
    position: absolute;
    top: 0;
    left: 98px;
    width: 4px;
    height: 200px;

    &:before,
    &:after {
      display: block;
      content: "";
      position: absolute;
      width: 4px;
      height: 25px;
      top: 0;
      left: 0;
      border-radius: 2px;
      background: white;
    }

    &:after {
      top: auto;
      bottom: 0;
    }
  }

  .s2 {
    transform: rotate(45deg);
  }
  .s3 {
    transform: rotate(90deg);
  }
  .s4 {
    transform: rotate(135deg);
  }
}

.triangleSparkles {
  position: absolute;
  width: 200px;
  height: 200px;
  top: 105px;
  left: 103px;
  animation: triangleSparkles 5s ease-in-out infinite;

  .sparkle {
    position: absolute;
    top: 0;
    left: 98px;
    width: 4px;
    height: 200px;

    &:before,
    &:after {
      display: block;
      content: "";
      position: absolute;
      width: 4px;
      height: 25px;
      top: 0;
      left: 0;
      border-radius: 2px;
      background: white;
    }
  }

  .s1 {
    top: 10px;
  }
  .s2 {
    transform: rotate(125deg);
  }
  .s3 {
    transform: rotate(235deg);
  }
}

@keyframes circle {
  0% {
    transform: translate3d(0, -300px, 0) scaleY(1.2);
  }
  10% {
    transform: translate3d(0, 50px, 0) scaleY(0.8);
  }
  14% {
    transform: translate3d(0, -30px, 0) scaleY(1.1);
  }
  18% {
    transform: translate3d(0, 10px, 0) scaleY(0.9);
  }
  20%,
  22% {
    transform: translate3d(0, 0, 0) scaleY(1);
  }
  26%,
  80% {
    transform: translate3d(0, 0, 0) scale(1.2);
  }
  32%,
  74% {
    transform: translate3d(0, 0, 0) scale(0);
  }
  84% {
    transform: translate3d(0, 0, 0) scale(0.9);
  }
  86%,
  88% {
    transform: translate3d(0, 0, 0) scale(1);
  }
  92% {
    transform: translate3d(0, -30px, 0) scaleY(0.9);
  }
  100% {
    transform: translate3d(0, 300px, 0) scaleY(1.2);
  }
}

@keyframes circleRing {
  0%,
  74% {
    transform: scale(0);
    opacity: 1;
  }
  80% {
    opacity: 1;
  }
  84%,
  100% {
    transform: scale(1.4);
    opacity: 0;
  }
}

@keyframes triangle {
  0%,
  52%,
  76%,
  100% {
    transform: scale(0);
  }
  58%,
  70% {
    transform: scale(1.2);
  }
  62% {
    transform: scale(0.9);
  }
  64%,
  66% {
    transform: scale(1);
  }
}

@keyframes triangleSparkles {
  0%,
  52% {
    transform: scale(0);
    opacity: 1;
  }
  58% {
    opacity: 1;
  }
  62%,
  100% {
    transform: scale(1.4);
    opacity: 0;
  }
}

@keyframes octagon {
  0%,
  30%,
  54%,
  100% {
    transform: scale(0);
  }
  36%,
  48% {
    transform: scale(1.2);
  }
  40% {
    transform: scale(0.9);
  }
  42%,
  44% {
    transform: scale(1);
  }
}

@keyframes octagonSparkles {
  0%,
  30% {
    transform: scale(0);
    opacity: 1;
  }
  36% {
    opacity: 1;
  }
  40%,
  100% {
    transform: scale(1.4);
    opacity: 0;
  }
}

</style>

<div class="background">
  <div class="circle"></div>
  <div class="circleRing"></div>
  <svg class="octagon">
    <polygon points="30,0 70,0 100,30 100,70 70,100 30,100 0,70 0,30" />
  </svg>
  <div class="octagonSparkles">
    <div class="sparkle s1"></div>
		<div class="sparkle s2"></div>
		<div class="sparkle s3"></div>
		<div class="sparkle s4"></div>
  </div>
  <svg class="triangle">
    <polygon points="53,0 106,90 0,90" />
  </svg>
  <div class="triangleSparkles">
    <div class="sparkle s1"></div>
		<div class="sparkle s2"></div>
		<div class="sparkle s3"></div>
  </div>
</div>