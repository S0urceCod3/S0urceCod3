# 👋 Welcome to s0urceCod3's GitHub Profile!

## 🛠️ Skills and Tools
- **Programming Languages**:  
  - 🌟 Basic knowledge of **C++** , **MySQL** , **PHP**
  - 💻 Proficient in **HTML**, **CSS**, and **JavaScript**  
- **Design**:  
  - 🎨 Skilled in **Figma** for creating modern and clean designs  
- **Tools**:  
  - 🛠️ I code using **Visual Studio Code**  

---

## 🌐 Connect with Me  
- 💬 **Discord**: `your-discord-handle`  
- 🐦 **X (Twitter)**: [Your Profile](https://x.com/your-profile)  
- 📱 **Telegram**: [Your Profile](https://t.me/your-profile)  

---

## ☕ Support Me  
If you enjoy my work, consider supporting me:  
[![Buy Me a Coffee](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/yourprofile)

---

## 🎥 GIF Section  
![Your GIF here](link-to-your-gif)  
*Replace the above link with a URL to your favorite GIF or animation.*  

---

## 🎮 Fun Corner: Play a Game!  

Enjoy a quick game of **Snake** directly in this README:  

```html
<canvas id="gameCanvas" width="400" height="400"></canvas>
<script>
let canvas = document.getElementById('gameCanvas');
let ctx = canvas.getContext('2d');
let box = 20, snake = [{ x: 9 * box, y: 10 * box }], food = {
  x: Math.floor(Math.random() * 19 + 1) * box,
  y: Math.floor(Math.random() * 19 + 1) * box
};
let direction, score = 0;

document.addEventListener('keydown', changeDirection);
function changeDirection(event) {
  if (event.key === 'ArrowUp' && direction !== 'DOWN') direction = 'UP';
  else if (event.key === 'ArrowDown' && direction !== 'UP') direction = 'DOWN';
  else if (event.key === 'ArrowLeft' && direction !== 'RIGHT') direction = 'LEFT';
  else if (event.key === 'ArrowRight' && direction !== 'LEFT') direction = 'RIGHT';
}

function draw() {
  ctx.fillStyle = 'black';
  ctx.fillRect(0, 0, canvas.width, canvas.height);
  for (let i = 0; i < snake.length; i++) {
    ctx.fillStyle = i === 0 ? 'green' : 'lightgreen';
    ctx.fillRect(snake[i].x, snake[i].y, box, box);
  }
  ctx.fillStyle = 'red';
  ctx.fillRect(food.x, food.y, box, box);

  let snakeX = snake[0].x, snakeY = snake[0].y;
  if (direction === 'UP') snakeY -= box;
  if (direction === 'DOWN') snakeY += box;
  if (direction === 'LEFT') snakeX -= box;
  if (direction === 'RIGHT') snakeX += box;

  if (snakeX === food.x && snakeY === food.y) {
    score++;
    food = {
      x: Math.floor(Math.random() * 19 + 1) * box,
      y: Math.floor(Math.random() * 19 + 1) * box
    };
  } else snake.pop();

  let newHead = { x: snakeX, y: snakeY };
  if (snakeX < 0 || snakeY < 0 || snakeX >= canvas.width || snakeY >= canvas.height || collision(newHead, snake)) {
    clearInterval(game);
    alert(`Game Over! Your score: ${score}`);
  }
  snake.unshift(newHead);
}

function collision(head, array) {
  for (let i = 0; i < array.length; i++) if (head.x === array[i].x && head.y === array[i].y) return true;
  return false;
}

let game = setInterval(draw, 100);
</script>
