<script setup>
import { computed, ref } from 'vue';

const props = defineProps({
  job: Object
})

const showFullDescription = ref(false);

const toggleFullDescription = () => {
  showFullDescription.value = !showFullDescription.value;
}

const truncatedDescription = computed(() => {
  let description = props.job.description;

  if (!showFullDescription.value) {
    description = description.slice(0, 100) + "...";
  }

  return description;
})
</script>

<template>
  <div class="bg-white rounded-xl shadow-md relative">
    <div class="p-4">
      <div class="mb-6">
        <div class="text-gray-600 my-2">
          {{ job.type }}
        </div>

        <h3 class="text-xl font-bold">
          {{ job.title }}
        </h3>
      </div>

      <h3 class="text-green-500 mb-2">
        {{ job.salary }} / Year
      </h3>

      <div class="mb-5 flex flex-col gap-4">
        <div>
          {{ truncatedDescription }}
        </div>
        
        <button
          @click="toggleFullDescription"
          class="cursor-pointer px-4 py-2 bg-green-500 hover:bg-green-600 text-white font-normal rounded-lg shadow-md hover:from-green-600 hover:to-green-700 transition duration-300"
        >
          show more
        </button>
      </div>

      <div class="border border-gray-100 mb-5"></div>

      <div class="flex flex-col lg:flex-row justify-between mb-4">
        <div class="text-teal-700 mb-3">
          <i class="pi pi-map-marker text-teal-700"></i>
          {{ job.location }}
        </div>
      </div>
    </div>
  </div>
</template>