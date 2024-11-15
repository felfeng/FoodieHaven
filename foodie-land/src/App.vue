<template>
  <div id="app">
    <nav class="navbar">
      <div class="navbar-logo">
        <img src="@/assets/icon.png" alt="Page Logo" class="logo" />
        <span class="title">FoodieLand</span>
      </div>

      <div class="navbar-right">
        <button @click="showModal = true" class="add-restaurant-btn">
          Add Restaurant
        </button>
        <button class="profile-btn">
          <img
            src="@/assets/profile.png"
            alt="User Profile"
            class="profile-icon"
          />
        </button>
      </div>
    </nav>

    <AddRestaurant
      v-if="showModal"
      @close="showModal = false"
      @add-restaurant="handleAddRestaurant"
    />
    <router-view />
  </div>
</template>

<script>
import AddRestaurant from "@/components/AddRestaurant.vue";

export default {
  name: "App",
  components: {
    AddRestaurant,
  },
  data() {
    return {
      showModal: false,
    };
  },
  methods: {
    handleAddRestaurant(restaurantData) {
      console.log("Restaurant added:", restaurantData);
    },
  },
};
</script>

<style>
body {
  background-color: #e3ecf1;
  margin: 0;
  font-family: "Libre Baskerville", serif;
  font-weight: 700;
}
</style>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  background-color: #003865;
  color: #fff;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
}

.navbar-logo {
  display: flex;
  align-items: center;
}

.logo {
  width: 40px;
  height: 40px;
  margin-right: 10px;
}

.title {
  font-size: 1.5em;
  font-weight: bold;
}

.navbar-right {
  display: flex;
  align-items: center;
}

.add-restaurant-btn {
  margin-right: 20px;
  padding: 8px 16px;
  background-color: white;
  color: #003865;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1em;
  font-weight: 700;
  font-family: "Libre Baskerville", serif;
}

.add-restaurant-btn:hover {
  background-color: #bdd6e6;
}

.profile-btn {
  background: none;
  border: none;
  cursor: pointer;
}

.profile-icon {
  width: 35px;
  height: 35px;
  border-radius: 50%;
}
</style>
