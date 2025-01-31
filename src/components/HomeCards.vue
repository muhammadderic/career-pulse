<script setup>
import Card from './HomeCard.vue';
</script>

<template>
  <section class="py-4">
    <div class="container-xl lg:container m-auto">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">
        <Card>
          <h2 class="text-2xl font-bold">
            For Job Seekers
          </h2>

          <p class="mt-2 mb-4">
            Unlock your dream career today—explore opportunities tailored just for you and take the first step toward a brighter future!
          </p>

          <a href="/" class="inline-block bg-black text-white rounded-lg px-4 py-2 hover:bg-gray-700">
            Browse Jobs
          </a>
        </Card>

        <Card bg="bg-green-200">
          <h2 class="text-2xl font-bold">
            For Recruiters
          </h2>

          <p class="mt-2 mb-4">
            Unlock top talent for your team today—post your job with us and connect with the best candidates in just a few clicks!
          </p>

          <a href="/" class="inline-block bg-green-500 text-white rounded-lg px-4 py-2 hover:bg-green-600">
            Add Job
          </a>
        </Card>
      </div>
    </div>
  </section>
</template>