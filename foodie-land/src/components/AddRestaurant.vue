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
  padding: 40px;
  border-radius: 8px;
  width: 550px;
  max-width: 90%;
  margin-bottom: 20px;
}

.modal-content h2 {
  text-align: center;
  margin-bottom: 5px;
  font-weight: 900;
}

.modal-content label {
  text-align: left;
  margin-bottom: 5px;
}

.modal-content form {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
}

label {
  display: block;
  margin-bottom: 5px;
  text-align: left;
  width: 100%;
  font-weight: 700;
}

input {
  margin-bottom: 20px;
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}

.save-btn {
  background-color: #4f2c1d;
  color: white;
  padding: 8px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-family: "Libre Baskerville", serif;
  font-weight: 700;
  font-size: 17px;
  width: 100%;
  box-shadow: border-box;
  margin-top: 6px;
}

.save-btn:hover {
  background-color: #2d1911;
}
</style>
