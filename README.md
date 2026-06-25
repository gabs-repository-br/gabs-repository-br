### OLÁ REDE 👋
#### IN PROGRESS 💪

<img width=100% src="[https://capsule-render.vercel.app/api?type=waving&color=00bfbf&height=120&section=header](https://capsule-render.vercel.app/api?typ=waving&height=300&color=gradient&text=Input%20text&descAlign=56&descAlignY=44&animation=blinking)"/>

[![Typing SVG](https://readme-typing-svg.herokuapp.com/?color=00bfbf&size=35&center=true&vCenter=true&width=1000&lines=HELLO,+MY+NAME+is+Gabriel+de+Souza+Correia;I'm+22+years+old;I+from+Brasil,+SP;I+study+software+Engineering+at+Unasp;Be+Welcome!+:%29)](https://git.io/typing-svg)








<div align="center">  
  <img width="49%" height="195px" src="https://github-readme-stats.vercel.app/api?username=gszbiel&show_icons=true&count_private=true&hide_border=true&title_color=00bfbf&icon_color=00bfbf&text_color=c9d1d9&bg_color=0d1117" alt="Gabriel de Souza Correia github stats" /> 
  <img width="41%" height="195px" src="https://github-readme-stats.vercel.app/api/top-langs/?username=gszbiel&layout=compact&hide_border=true&title_color=00bfbf&text_color=00bfbf&bg_color=0d1117" />
</div>

### Main skills:
  

### Tools:
![Visual Studio Code](https://img.shields.io/badge/-Visual%20Studio%20Code-0D1117?style=for-the-badge&logo=visual-studio-code&logoColor=007ACC&labelColor=0D1117)&nbsp;
<!-- ![Git](https://img.shields.io/badge/-Git-0D1117?style=for-the-badge&logo=git&labelColor=0D1117)&nbsp; -->
![GitHub](https://img.shields.io/badge/-GitHub-0D1117?style=for-the-badge&logo=github&labelColor=0D1117)&nbsp;
![Windows](https://img.shields.io/badge/-Windows-0D1117?style=for-the-badge&logo=windows&labelColor=0D1117)&nbsp;
![microsoft-office](https://img.shields.io/badge/-microsoft_office-0D1117?style=for-the-badge&logo=microsoft-office&labelColor=0D1117)&nbsp;

### Other Knowledge:
![Python](https://img.shields.io/badge/-python-0D1117?style=for-the-badge&logo=python&logoColor=1572B6&labelColor=0D1117)&nbsp;
![MySQL](https://img.shields.io/badge/-mysql-0D1117?style=for-the-badge&logo=mysql&labelColor=0D1117)&nbsp;
![Figma](https://img.shields.io/badge/-figma-0D1117?style=for-the-badge&logo=figma&labelColor=0D1117)&nbsp;
  
### Studying in this moment:
![JavaScript](https://img.shields.io/badge/-JavaScript-0D1117?style=for-the-badge&logo=javascript&labelColor=0D1117&textColor=0D1117)&nbsp;

<div>
    <script src="script.js"></script>
</body>
</html>
style.css
body {
    background: #111;
    color: white;
    text-align: center;
    font-family: Arial, sans-serif;
}

canvas {
    background: #222;
    border: 3px solid #4CAF50;
    margin-top: 20px;
}
script.js
const canvas = document.getElementById("game");
const ctx = canvas.getContext("2d");

const box = 20;
const canvasSize = 400;

let snake = [
    { x: 200, y: 200 }
];

let direction = "RIGHT";

let food = {
    x: Math.floor(Math.random() * 20) * box,
    y: Math.floor(Math.random() * 20) * box
};

document.addEventListener("keydown", changeDirection);

function changeDirection(event) {
    if (event.key === "ArrowUp" && direction !== "DOWN")
        direction = "UP";

    if (event.key === "ArrowDown" && direction !== "UP")
        direction = "DOWN";

    if (event.key === "ArrowLeft" && direction !== "RIGHT")
        direction = "LEFT";

    if (event.key === "ArrowRight" && direction !== "LEFT")
        direction = "RIGHT";
}

function draw() {
    ctx.fillStyle = "#222";
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Cobra
    snake.forEach((segment, index) => {
        ctx.fillStyle = index === 0 ? "#4CAF50" : "#8BC34A";
        ctx.fillRect(segment.x, segment.y, box, box);
    });

    // Comida
    ctx.fillStyle = "red";
    ctx.fillRect(food.x, food.y, box, box);

    let headX = snake[0].x;
    let headY = snake[0].y;

    if (direction === "UP") headY -= box;
    if (direction === "DOWN") headY += box;
    if (direction === "LEFT") headX -= box;
    if (direction === "RIGHT") headX += box;

    // Comer comida
    if (headX === food.x && headY === food.y) {
        food = {
            x: Math.floor(Math.random() * 20) * box,
            y: Math.floor(Math.random() * 20) * box
        };
    } else {
        snake.pop();
    }

    const newHead = { x: headX, y: headY };

    // Colisão
    if (
        headX < 0 ||
        headY < 0 ||
        headX >= canvasSize ||
        headY >= canvasSize ||
        snake.some(segment => segment.x === headX && segment.y === headY)
    ) {
        clearInterval(game);
        alert("Game Over!");
    }

    snake.unshift(newHead);
}

const game = setInterval(draw, 100);
  
</div>
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=00bfbf&height=120&section=footer"/>****
