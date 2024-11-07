<template>
    <div class="modal-overlay" @click.self="closeModal">
      <div class="modal-content">
        <h2>Add Restaurant</h2>
        <form @submit.prevent="submitForm">
          <label>Restaurant Name:</label>
          <input type="text" v-model="name" required />
  
          <label>Location:</label>
          <input type="text" v-model="location" required />
  
          <button type="submit" class="save-btn">Save Bookmark</button>
        </form>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "AddRestaurant",
    data() {
      return {
        name: "",
        location: "",
        videoLink: "",
      };
    },
    methods: {
      closeModal() {
        this.$emit("close");
      },
      submitForm() {
        this.$emit("add-restaurant", {
          name: this.name,
          location: this.location,
          videoLink: this.videoLink,
        });
        this.closeModal();
      },
    },
  };
  </script>
  
  <style scoped>
  .modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
  }
  
  .modal-content {
    background: white;
    padding: 20px;
    border-radius: 8px;
    width: 300px;
    max-width: 80%;
  }
  
  .save-btn {
    background-color: #4CAF50;
    color: white;
    padding: 10px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  
  .save-btn:hover {
    background-color: #45a049;
  }
  </style>
  