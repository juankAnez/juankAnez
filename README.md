<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:3B6D11,100:639922&height=120&section=header&text=juankAnez&fontSize=40&fontColor=fff&animation=fadeIn&fontAlignY=38&desc=Full%20Stack%20Developer%20·%20building%20stuff%20that%20ships&descAlignY=60&descAlign=50"/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1000&color=639922&center=true&vCenter=true&width=500&lines=Full+Stack+Developer+%F0%9F%9A%80;Python+%2B+React+%2B+Node.js+%E2%9C%A8;AI+%2B+Web+%2B+Backend+%F0%9F%A4%96;Always+learning%2C+always+building+%F0%9F%94%A5)](https://git.io/typing-svg)

</div>

---

## 👤 About Me

<table>
<tr>
<td valign="top" width="50%">

### 🇪🇸 Español
Soy un desarrollador Full Stack apasionado por construir soluciones digitales que impacten. Me especializo en el desarrollo web moderno, integrando tecnologías de frontend y backend con herramientas de IA para crear productos escalables y eficientes.

- 🌍 Basado en Colombia
- 🚀 Siempre aprendiendo algo nuevo
- 🤖 Apasionado por la IA y la automatización
- 💡 Me encanta resolver problemas complejos con código limpio

</td>
<td valign="top" width="50%">

### 🇺🇸 English
I'm a passionate Full Stack Developer focused on building digital solutions that make an impact. I specialize in modern web development, combining frontend and backend technologies with AI tools to create scalable and efficient products.

- 🌍 Based in Colombia
- 🚀 Always learning something new
- 🤖 Passionate about AI and automation
- 💡 I love solving complex problems with clean code

</td>
</tr>
</table>

---

## 🛠️ Tech Stack

<div align="center">

### 🎨 Frontend
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Angular](https://img.shields.io/badge/Angular-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

### ⚙️ Backend
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)

### 🗄️ Databases
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Oracle](https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=oracle&logoColor=white)

### 🤖 AI & Tools
![ChatGPT](https://img.shields.io/badge/ChatGPT-74aa9c?style=for-the-badge&logo=openai&logoColor=white)
![GitHub Copilot](https://img.shields.io/badge/GitHub_Copilot-000000?style=for-the-badge&logo=github&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

</div>

---

## 📊 GitHub Stats

<div align="center">


</div>

<div align="center">

<img width="70%" src="https://github-readme-streak-stats.herokuapp.com/?user=juankAnez&theme=tokyonight&hide_border=true"/>

</div>

<div align="center">

<img width="70%" src="https://github-readme-activity-graph.vercel.app/graph?username=juankAnez&theme=tokyo-night&hide_border=true&area=true"/>

</div>

---

## 🐍 Easter Egg: Snake Game

¿Aburrido de gestionar citas? ¡Juega Snake directamente desde el panel administrativo de **KAIROS**!

```html
<!-- Código completo del juego (versión HTML + CSS + JS puro) -->
<!DOCTYPE html>
<html>
<head>
<style>
  body { display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; background: #1a1a2e; }
  canvas { border: 2px solid #c9a84c; background: #16213e; }
  .score { color: #c9a84c; font-family: Arial; font-size: 20px; text-align: center; margin-bottom: 10px; }
</style>
</head>
<body>
<div>
  <div class="score">Puntuación: <span id="score">0</span></div>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
</div>
<script>
// Configuración del juego
const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');
const gridSize = 20;
const tileCount = canvas.width / gridSize;

let snake = [{x: 10, y: 10}];
let direction = {x: 0, y: 0};
let food = {x: 15, y: 10};
let score = 0;
let gameOver = false;

function generateFood() {
  food = {
    x: Math.floor(Math.random() * tileCount),
    y: Math.floor(Math.random() * tileCount)
  };
  if (snake.some(segment => segment.x === food.x && segment.y === food.y)) {
    generateFood();
  }
}

function draw() {
  ctx.fillStyle = '#16213e';
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  ctx.fillStyle = '#4ade80';
  snake.forEach((segment, index) => {
    ctx.fillRect(segment.x * gridSize, segment.y * gridSize, gridSize-2, gridSize-2);
  });

  ctx.fillStyle = '#f87171';
  ctx.beginPath();
  ctx.arc(food.x * gridSize + gridSize/2, food.y * gridSize + gridSize/2, gridSize/2-2, 0, Math.PI * 2);
  ctx.fill();
}

function update() {
  if (gameOver) return;

  const head = {x: snake[0].x + direction.x, y: snake[0].y + direction.y};

  if (head.x < 0 || head.x >= tileCount || head.y < 0 || head.y >= tileCount) {
    gameOver = true;
    alert('¡Game Over! Puntuación: ' + score);
    return;
  }

  if (snake.some(segment => segment.x === head.x && segment.y === head.y)) {
    gameOver = true;
    alert('¡Game Over! Puntuación: ' + score);
    return;
  }

  snake.unshift(head);

  if (head.x === food.x && head.y === food.y) {
    score++;
    document.getElementById('score').textContent = score;
    generateFood();
  } else {
    snake.pop();
  }
}

function gameLoop() {
  update();
  draw();
  setTimeout(gameLoop, 130);
}

document.addEventListener('keydown', (e) => {
  switch(e.key) {
    case 'ArrowUp': if (direction.y === 0) { direction = {x: 0, y: -1}; } break;
    case 'ArrowDown': if (direction.y === 0) { direction = {x: 0, y: 1}; } break;
    case 'ArrowLeft': if (direction.x === 0) { direction = {x: -1, y: 0}; } break;
    case 'ArrowRight': if (direction.x === 0) { direction = {x: 1, y: 0}; } break;
  }
});

generateFood();
gameLoop();
</script>
</body>
</html>
