<template>
  <div class="flex flex-col items-center justify-center min-h-screen p-4 bg-gradient-to-br from-purple-400 to-pink-300">
    <img alt="User Avatar" class="w-32 h-32 rounded-full border-4 border-white shadow-lg mb-4 transform hover:scale-105 transition-transform duration-300" src="./assets/user-avatar.jpg" />
    <h1 class="text-4xl font-bold text-white mb-2 font-kanit">{{ user.name }}</h1>
    <p class="text-lg text-gray-100 text-center mb-6 max-w-md font-kanit">{{ user.description }}</p>

    <div class="flex gap-6 w-full max-w-xs justify-center">
      <a href="https://instagram.com" target="_blank" class="transform hover:scale-110 transition-transform duration-200">
        <img src="./assets/instagram-icon.png" alt="Instagram" class="w-10 h-10" />
      </a>
      <a href="https://facebook.com" target="_blank" class="transform hover:scale-110 transition-transform duration-200">
        <img src="./assets/facebook-icon.png" alt="Facebook" class="w-10 h-10" />
      </a>
      <a href="https://line.me" target="_blank" class="transform hover:scale-110 transition-transform duration-200">
        <img src="./assets/line-icon.png" alt="Line" class="w-10 h-10" />
      </a>
    </div>
  </div>
</template>

<script setup>
const user = {
  name: 'Txmmy Shop',
  description: '֗ ִ💫 ˑ open 10:00 - 23:00 𓈒♡̆̈꒦꒷🍒 แอดแล้วทักมานะคะ 🧸 ⤾ไม่ตอบทักไลน์ ID : txmmy_25'
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@400;700&display=swap');

.font-kanit {
  font-family: 'Kanit', sans-serif;
}

/* Tailwind and DaisyUI will handle most styling, no need for additional styles here */
</style>
