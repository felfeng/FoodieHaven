<template>
    <div class="card">
      <img :src="listing.image" alt="Restaurant Image" />
      <h3>{{ listing.name }}</h3>
      <p>{{ listing.cuisineType }}</p>
      <p>{{ listing.location }}</p>
      <button @click="viewDetails">View Details</button>
    </div>
  </template>
  
  <script>
  export default {
    name: "ListingCard",
    props: {
      listing: Object,
    },
    methods: {
      viewDetails() {
        // This can route to a detailed view if needed
        console.log("Viewing details for:", this.listing.name);
      },
    },
  };
  </script>
  
  <style scoped>
  .card {
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 10px;
    text-align: center;
  }
  .card img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 5px;
  }
  </style>
  