<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  const cards = document.querySelectorAll('.card');
  let startX, currentX, offsetX, currentCard, isDragging = false;

  cards.forEach(card => {
    card.addEventListener('mousedown', startDrag);
    card.addEventListener('touchstart', startDrag);

    card.addEventListener('mousemove', drag);
    card.addEventListener('touchmove', drag);

    card.addEventListener('mouseup', endDrag);
    card.addEventListener('touchend', endDrag);

    card.addEventListener('mouseleave', endDrag);
  });

  function startDrag(event) {
    isDragging = true;
    currentCard = event.target;
    currentCard.classList.add('dragging');
    startX = event.type.includes('mouse') ? event.clientX : event.touches[0].clientX;
  }

  function drag(event) {
    if (!isDragging) return;

    currentX = event.type.includes('mouse') ? event.clientX : event.touches[0].clientX;
    offsetX = currentX - startX;

    currentCard.style.transform = `translateX(${offsetX}px) rotate(${offsetX * 0.1}deg)`;
  }

  function endDrag() {
    if (!isDragging) return;

    isDragging = false;
    currentCard.classList.remove('dragging');

    // Determine if the card was swiped far enough
    if (Math.abs(offsetX) > 100) {
      const direction = offsetX > 0 ? 1 : -1;
      currentCard.style.transform = `translateX(${direction * 1000}px) rotate(${direction * 45}deg)`;
      currentCard.style.opacity = '0';
      currentCard.addEventListener('transitionend', () => {
        currentCard.remove();
        // Optional: Trigger next card in stack
        if (cards.length > 1) {
          cards[1].style.zIndex = parseInt(window.getComputedStyle(cards[1]).zIndex) + 1;
        }
      });

      if (direction === 1) {
        console.log(`SWIPE RIGHT!`)
      } else {
        console.log(`swipe left`)
      }
    } else {
      // Reset the card position
      currentCard.style.transform = 'translateX(0) rotate(0)';
    }
  }
})
</script>

<template>
  <div class="card-stack">

    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel, 28</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Vanessa, 26</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Elizabeth, 25</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Jack, 30</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Vin, 24</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name"></h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
    <div class="card" style="background-image: url('https://via.placeholder.com/300x500');"><h1 class="name">Daniel</h1></div>
  </div>
</template>

<style scoped>

.card-stack {
  position: absolute;
  width: 100%;
  height: 100%;
}

.name {
  position: absolute;
  bottom: 100px;
  left: 20px;
}

.card {
  position: absolute;
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  border-radius: 20px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.5s ease, opacity 0.5s ease;
}

.card:nth-child(1) {
  z-index: 12;
}

.card:nth-child(2) {
  z-index: 11;
}

.card:nth-child(3) {
  z-index: 10;
}

.card:nth-child(4) {
  z-index: 9;
}

.card:nth-child(5) {
  z-index: 8;
}

.card:nth-child(6) {
  z-index: 7;
}

.card:nth-child(7) {
  z-index: 6;
}

.card:nth-child(8) {
  z-index: 5;
}

.card:nth-child(9) {
  z-index: 4;
}

.card:nth-child(10) {
  z-index: 3;
}

.card:nth-child(11) {
  z-index: 2;
}

.card:nth-child(12) {
  z-index: 1;
}

</style>