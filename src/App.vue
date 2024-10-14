<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light custom-navbar">
      <div class="container-fluid">
        <router-link class="navbar-brand brand-name" to="/">VUE APPLICATION</router-link>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            
            <li class="nav-item">
              <router-link class="nav-link" to="/home">Home</router-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/products">Products</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <div class="main-content">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App'
};
</script>

<style scoped>
.custom-navbar {
  background-color: #f8f9fa;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.brand-name {
  font-family: 'Montserrat', sans-serif;
  font-weight: bold;
  color: #007bff;
}

.nav-link {
  font-size: 16px;
  color: #333;
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: #007bff;
}

.router-link-active {
  color: #007bff;
  font-weight: bold;
}

.main-content {
  padding: 20px;
  background-color: #f4f4f9;
  min-height: 80vh;
}

@media (max-width: 992px) {
  .navbar-nav {
    text-align: center;
    margin-top: 10px;
  }
}
</style>
