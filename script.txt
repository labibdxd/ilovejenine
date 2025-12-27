// Fade-in on scroll
const items = document.querySelectorAll('.fade');

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('show');
    }
  });
}, { threshold: 0.3 });

items.forEach(item => observer.observe(item));


// Floating emoji stickers
const container = document.querySelector('.floating-container');
const stickers = ['🤍', '✨', '♡'];

function createSticker() {
  const span = document.createElement('span');
  span.className = 'sticker';
  span.textContent = stickers[Math.floor(Math.random() * stickers.length)];

  span.style.left = Math.random() * 100 + 'vw';
  span.style.animationDuration = 6 + Math.random() * 4 + 's';

  container.appendChild(span);

  setTimeout(() => span.remove(), 10000);
}

setInterval(createSticker, 800);
