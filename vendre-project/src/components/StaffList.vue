<template>
    <div class="container mx-auto p-4">
      <div class="flex flex-col items-center">
        <StaffCard v-for="staff in staffList" :key="staff.id" :staff="staff" />
      </div>
      <div class="flex justify-center items-center mt-6 space-x-4">
        <button @click="fetchPage(page - 1)" :disabled="page === 1" class=" px-4 py-2 bg-gray-200 rounded disabled:opacity-50">Previous</button>
        <span>Page {{ page }} of {{ totalPages }}</span>
        <button @click="fetchPage(page + 1)" :disabled="page === totalPages" class="px-4 py-2 bg-gray-200 rounded disabled:opacity-50">Next</button>
      </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  import StaffCard from './StaffCard.vue';
  
  export default {
    components: {
      StaffCard
    },
    data() {
      return {
        staffList: [],
        page: 1,
        totalPages: 1,
      };
    },
    mounted() {
      this.fetchPage(this.page);
    },
    methods: {
      fetchPage(page) {
        axios.get(`https://reqres.in/api/users?page=${page}&per_page=6`)
          .then(response => {
            this.staffList = response.data.data;
            this.page = response.data.page;
            this.totalPages = response.data.total_pages;
          })
          .catch(error => {
            console.error(error);
          });
      }
    }
  }
  </script>
  