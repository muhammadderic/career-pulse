<script setup lang="ts">
import { computed, onMounted, reactive } from 'vue';
import JobListing from './JobListing.vue';
import axios from 'axios';

const props = defineProps({
  limit: {
    type: Number,
  },
});

const limitedJobs = computed(() => {
  // If no limit is provided, return all jobs
  return props.limit ? state.jobs.slice(0, props.limit) : state.jobs;
});


const state = reactive({
  jobs: [],
  isLoading: true,
})

onMounted(async () => {
  try {
    const response = await axios.get('/api/jobs');
    state.jobs = response.data;
  } catch (error) {
    console.error('Error fetching jobs:', error);
  } finally {
    state.isLoading = false;
  }
})
</script>

<template>
  <section class="bg-blue-50 px-4 py-10">
    <div class="container-xl lg:container m-auto">
      <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
        Browse Jobs
      </h2>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <JobListing
          v-for="job in limitedJobs"
          :key="job.id"
          :job="job"
        />
      </div>
    </div>
  </section>
</template>