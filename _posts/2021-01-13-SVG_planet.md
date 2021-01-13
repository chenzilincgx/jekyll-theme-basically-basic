---
layout: page
title: SVG实验
excerpt_separator: "<!--more-->"
tags:
        - SVG制作
---
    

<!--more-->
### 很多动态SVG可以从这里找到[SVG](https://codepen.io/)
 以下是我找到一个动态：

<svg viewBox="0 0 160 160" width="160" height="160">
  <circle cx="80" cy="80" r="50" />
  <g transform=" matrix(0.866, -0.5, 0.25, 0.433, 80, 80)">
    <path d="M 0,70 A 65,70 0 0,0 65,0 5,5 0 0,1 75,0 75,70 0 0,1 0,70Z" fill="#FFFF33">
      <animateTransform attributeName="transform" type="rotate" from="360 0 0" to="0 0 0" dur="1s" repeatCount="indefinite" />
    </path>
  </g>
  <path d="M 50,0 A 50,50 0 0,0 -50,0Z" transform="matrix(0.866, -0.5, 0.5, 0.866, 80, 80)" />
</svg>
可以在此基础上做一些改变
<svg viewBox="0 0 160 160" width="160" height="160">
  <circle cx="80" cy="80" r="50" />
  <g transform=" matrix(0.866, -0.5, 0.25, 0.433, 80, 80)">
    <path d="M 0,70 A 65,70 0 0,0 65,0 5,5 0 0,1 75,0 75,70 0 0,1 0,70Z" fill="#FFFF33">
      <animateTransform attributeName="transform" type="rotate" from="360 0 0" to="0 0 0" dur="1s" repeatCount="indefinite" />
    </path>
  </g>
  <path d="M 50,0 A 50,50 0 0,0 -50,0Z" transform="matrix(0.866, -0.5, 0.5, 0.866, 80, 80)" />
 <defs>
    <radialGradient id="ball" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
      <stop offset="0%" style="stop-color:rgb(255,255,255);stop-opacity:0" />
      <stop offset="100%" style="stop-color:rgb(0,0,255);stop-opacity:1" />
    </radialGradient>
  </defs>
 <g id="ball"    fill="url(#ball)" >
  <circle cx="80" cy="80" r="50"  />
</g>
</svg>
在原有的基础上加入以下代码，让星球颜色从黑色变成渐变蓝色
```
 <defs>
    <radialGradient id="ball" cx="50%" cy="50%" r="50%" fx="50%" fy="50%">
      <stop offset="0%" style="stop-color:rgb(255,255,255);stop-opacity:0" />
      <stop offset="100%" style="stop-color:rgb(0,0,255);stop-opacity:1" />
    </radialGradient>
  </defs>
 <g id="ball"    fill="url(#ball)" >
  <circle cx="80" cy="80" r="50"  />
</g>
```
