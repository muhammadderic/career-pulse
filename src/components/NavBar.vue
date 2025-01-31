<script setup>
  import logo from '@/assets/img/career_pulse_logo.jpg'
</script>

<template>
  <nav class="bg-white border-b">
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
      <div class="flex h-20 items-center justify-between">
        <div class="flex flex-1 items-center justify-center md:items-stretch md:justify-start">
          <!-- Logo -->
          <a href="/" class="flex flex-shrink-0 items-center mr-4">
            <img 
              class="h-8 w-auto" 
              :src="logo" 
              alt="Career Pulse Logo" 
            />

            <span class="hidden md:block text-black text-2xl font-bold ml-2">
              Career Pulse
            </span>
          </a>

          <!-- Navigation -->
          <div class="md:ml-auto">
            <div class="flex space-x-2">
              <a href="/" class="shadow-lg text-black hover:bg-gray-500 hover:text-white rounded-md px-3 py-2 border hover:border-0 border-black">
                Home
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>