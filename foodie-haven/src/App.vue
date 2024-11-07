<template>
  <div id="app">
    <nav class="navbar">
      <!-- Logo / Icon on the Left -->
      <div class="navbar-logo">
        <img src="@/assets/icon.png" alt="Page Logo" class="logo" />
        <span class="title">Foodie Haven</span>
      </div>
      
      <!-- Right Aligned Buttons -->
      <div class="navbar-right">
        <button @click="addRestaurant" class="add-restaurant-btn">Add Restaurant</button>
        <button class="profile-btn">
          <img src="@/assets/profile.png" alt="User Profile" class="profile-icon" />
        </button>
      </div>
    </nav>

    <!-- Main content for pages -->
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App",
  methods: {
    addRestaurant() {
      // Logic to open the add restaurant form goes here
      console.log("Add Restaurant button clicked");
    },
  },
};
</script>

<style scoped>
/* Navbar Styles */
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  background-color: #003865;
  color: #fff;
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
