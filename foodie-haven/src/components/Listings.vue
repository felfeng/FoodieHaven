<template>
    <div class="listings">
      <h1>Restaurant Listings</h1>
      <div class="listing-container">
        <ListingCard v-for="listing in listings" :key="listing.id" :listing="listing" />
      </div>
    </div>
  </template>
  
  <script>
  import ListingCard from "@/components/ListingCard.vue";
  
  export default {
    name: "Listings",
    components: {
      ListingCard,
    },
    data() {
      return {
        listings: [], // This will later be populated from API data
      };
    },
    mounted() {
      // Fetch data from your backend API here once it's available
    },
  };
  </script>
  
  <style scoped>
  .listings {
    padding: 20px;
  }
  .listing-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  }
  </style>
  