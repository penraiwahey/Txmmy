<template>
    <div class="relative">
      <p class="text-2xl text-purple-700 text-left w-full max-w-lg mb-4 px-4 font-kanit">กลุ่มสุดปัง</p>
      <div class="carousel flex overflow-x-auto gap-6 p-4 w-full max-w-lg bg-white bg-opacity-30 rounded-2xl shadow-lg backdrop-blur-sm border border-purple-200">
        <div
          v-for="(item, index) in items"
          :key="index"
          class="carousel-item flex-shrink-0 w-80 transition-transform duration-300 transform hover:scale-105"
        >
          <div class="card bg-purple-100 shadow-xl rounded-xl transition-shadow duration-300 hover:shadow-2xl w-80">
            <figure class="px-8 pt-8">
              <img
                :src="item.image"
                alt="'Sample Image ' + (index + 1)"
                class="rounded-xl h-48 object-cover"
                loading="lazy"
                @error="onImageError"
              />
            </figure>
            <div class="card-body items-center text-center">
              <h2 class="card-title text-purple-800 font-semibold font-kanit">{{ item.title }}</h2>
              <p class="text-purple-600 font-kanit">{{ item.description }}</p>
              <div class="card-actions justify-center mt-4">
                <a :href="item.link" target="_blank" class="btn btn-purple w-36 font-kanit" aria-label="ดูตัวอย่างของ {{ item.title }}">ดูตัวอย่าง</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  
  <script setup>
  import { defineProps } from 'vue';
  
  const props = defineProps({
    items: {
      type: Array,
      required: true,
    },
  });
  
  const onImageError = (event) => {
    event.target.src = './assets/placeholder-image.png'; // Fallback image
  };
  </script>
  
  <style scoped>
  .carousel-item {
    transition: transform 0.3s;
  }
  
  .card {
    transition: box-shadow 0.3s;
  }
  
  .btn-purple {
    background-color: #a855f7; /* Adjust this for a nice purple */
    color: white;
  }
  
  .btn-purple:hover {
    background-color: #9333ea; /* Darker purple on hover */
  }
  
  /* Responsive adjustments */
  @media (max-width: 768px) {
    .carousel-item {
      width: 80vw; /* Set width to 80% of the viewport */
      max-width: 300px; /* Max width to prevent it from getting too wide */
    }
  
    .card {
      width: 100%; /* Full width for the card */
    }
  }
  </style>
  