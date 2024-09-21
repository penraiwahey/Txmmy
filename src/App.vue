<template>
    <div class="flex flex-col items-center justify-center min-h-screen p-6 bg-gradient-to-br from-purple-300 via-purple-400 to-pink-300">
      <div class="p-6 text-center font-kanit bg-white bg-opacity-80 rounded-lg shadow-lg mt-32">
        <div class="relative group mb-6 flex justify-center items-center h-48 mt">
          <img
            alt="User Avatar for Txmmy Shop"
            class="rounded-full border-4 border-white shadow-xl mb-2 animate-scale"
            src="./assets/user-avatar.jpg"
          />
        </div>
  
        <h1 class="text-4xl font-bold text-purple-800 mb-1 transition-transform duration-300 hover:scale-105">{{ user.name }}</h1>
        <p class="text-lg text-gray-600 text-center mb-4 px-4 max-w-md transition-opacity duration-300">{{ user.description }}</p>
  
        <!-- Social Media Links -->
        <div class="flex gap-6 justify-center mb-4">
          <a href="https://instagram.com" target="_blank" aria-label="Visit Instagram" class="hover:scale-125 transition-transform duration-300">
            <img src="./assets/instagram-icon.png" alt="Instagram Icon" class="w-10 h-10" />
          </a>
          <a href="https://www.facebook.com/Fiw.luxU" target="_blank" aria-label="Visit Facebook" class="hover:scale-125 transition-transform duration-300">
            <img src="./assets/facebook-icon.png" alt="Facebook Icon" class="w-10 h-10" />
          </a>
          <a href="https://line.me" target="_blank" aria-label="Visit Line" class="hover:scale-125 transition-transform duration-300">
            <img src="./assets/line-icon.png" alt="Line Icon" class="w-10 h-10" />
          </a>
        </div>
  
        <!-- Scroll Indicator -->
        <div class="mt-4 animate-bounce text-purple-600 opacity-80">
          <span class="text-1xl font-kanit">▼ เลื่อนเพื่อดูกลุ่มได้เลยงับ</span>
        </div>
      </div>
  
      <!-- Carousel Section -->
      <div ref="carouselSection" class="opacity-0 transition-opacity duration-1000 ease-in-out transform translate-y-10 mt-8 w-full max-w-lg">
        <Carousel :items="carouselItems" />
      </div>
    </div>
  </template>
  
  <script setup>
  import { onMounted, onUnmounted, ref } from 'vue';
  import Carousel from './components/Carousel.vue';
  
  // Import images
  import image1 from './assets/1.jpg';
  import image2 from './assets/2.jpg';
  import image3 from './assets/3.jpg';
  import image4 from './assets/4.jpg';
  import image5 from './assets/5.jpg';
  import image6 from './assets/6.jpg';
  
  const user = {
    name: 'Txmmy Shop',
    description: '💫 ˑ open 10:00 - 23:00 𓈒♡̆̈🍒 แอดแล้วทักมานะคะ 🧸 ⤾ไม่ตอบทักไลน์ ID : txmmy_25'
  };
  
  const carouselItems = [
  {
    image: image1,
    title: 'Mate Room My Little',
    description: 'กลุ่มคนสวยผมฟ้า',
    link: 'https://drive.google.com/drive/folders/1YXZvZzs0uATf_SOqwQDGodSRkV-FnbTZ',
  },
  {
    image: image2,
    title: 'MUMUJAM',
    description: 'กลุ่มมุมุแจ้ม',
    link: 'https://drive.google.com/drive/folders/1e_w3wEUKYVSxlWzWnP9ckoc3fjStDUDa?usp=drive_link',
  },
  {
    image: image3,
    title: 'PAPHICH',
    description: 'กลุ่มสอนทำป้ายแนวเฮด',
    link: 'https://drive.google.com/drive/folders/19kF4QIHZOnNE9f3ED6sCCmbzbrBPfHlD',
  },
  {
    image: image4,
    title: 'Yume bloom',
    description: '💫ยูเมะ บลูม✨งานลงสีเฉพาะกลุ่ม ดีเทลน่ารักฝลดไฝล อัพ 25 เซต 👉🏻💖👈🏻เติมความตะมุตะมิให้งานของคุณ⭐️',
    link: 'https://drive.google.com/drive/folders/11GDPSiBkvMVa5AY3bwC3jhJIRGgzr4K8',
  },
  {
    image: image5,
    title: 'Runbun',
    description: 'กลุ่มตูนเฉพาะกลุ่ม',
    link: 'https://drive.google.com/drive/folders/13oAQZXed6CuJtZy2f0a84muhZCUm_wIN',
  },
  {
    image: image6,
    title: 'Churak Churose',
    description: '🌷กลุ่มบล็อกเฉพาะชูรักชูโรส v.2💗99฿ 💗ทะยอยอัพจนครบ 25 บล็อกสายน่ารักนุ้บนิ้บ ห้ามพลาด!แอดดึงไว ไม่เทแน่นอนค่า✨💝ตยจิ้มเลยน้า💝 ',
    link: 'https://drive.google.com/drive/folders/1-4ZyOp3-kJlXgwmYL5tJ9JPapZsCvwoD',
  },
];

  
  const carouselSection = ref(null);
  
  onMounted(() => {
    const handleScroll = () => {
  const carouselPosition = carouselSection.value.getBoundingClientRect().top;
  const windowHeight = 650;

  console.log('Carousel Position:', carouselPosition);
  console.log('Window Height:', windowHeight);
  
  if (carouselPosition <= windowHeight * 0.8 && carouselPosition > 0) {
    if (!carouselSection.value.classList.contains('opacity-100')) {
      carouselSection.value.classList.add('opacity-100', 'translate-y-0');
      carouselSection.value.classList.remove('opacity-0', 'translate-y-10');
    }
  } else if (carouselPosition > windowHeight) {
    if (carouselSection.value.classList.contains('opacity-100')) {
      carouselSection.value.classList.remove('opacity-100', 'translate-y-0');
      carouselSection.value.classList.add('opacity-0', 'translate-y-10');
    }
  }
}; // ตรวจสอบว่า semicolon ที่นี่ถูกต้อง




  
    window.addEventListener('scroll', handleScroll);
  
    // Clean up event listener on component unmount
    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll);
    });
  });
  </script>
  
  <style>
  @import url('https://fonts.googleapis.com/css2?family=Kanit:wght@400;700&display=swap');
  
  .font-kanit {
    font-family: 'Kanit', sans-serif;
  }
  .carousel {
    width: 100%; /* Ensure the carousel uses the full width */
  }
  
  .carousel-item {
    flex: 0 0 auto; /* Prevent flex items from growing */
    width: 90%; /* Default width */
    max-width: 400px; /* Max width for larger screens */
  }
  .opacity-100 {
    opacity: 1 !important;
  }
  
  .translate-y-0 {
    transform: translateY(0) !important;
  }
  
  .bg-white {
    background-color: rgba(255, 255, 255, 0.1);
  }
  .opacity-0 {
    opacity: 0;
    transition: opacity 0.5s ease, transform 0.5s ease; /* เพิ่ม transition ที่นี่ */
}
.opacity-100 {
    opacity: 1;
    transition: opacity 0.5s ease, transform 0.5s ease; /* เพิ่ม transition ที่นี่ */
}
@keyframes scale-in-out {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
}
.animate-scale {
  animation: scale-in-out 3s ease-in-out infinite; /* ปรับความเร็วที่นี่ */
}
  </style>
  