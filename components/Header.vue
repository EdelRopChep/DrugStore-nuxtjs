<!-- components/Header.vue -->
<template>
 <header class="header">
      <div class="logo-container">
        <img src="~/assets/logo.png" alt="Drug Store Logo" class="logo">
      </div>
      <nav class="navigation">
        <ul class="nav-list">
          <li class="nav-item"><NuxtLink to="/" class="nav-link">Home</NuxtLink></li>
          <li class="nav-item"><NuxtLink to="/products" class="nav-link">About</NuxtLink></li>
          <li class="nav-item"><NuxtLink to="/services" class="nav-link">Services</NuxtLink></li>
          <li class="nav-item"><NuxtLink to="/contact" class="nav-link">Contact</NuxtLink></li>
        </ul>
      </nav>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header'
  }
  </script>
  
  <style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background-color: #dc06dc;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  }
  
  .logo-container {
    flex: 0 0 auto;
  }
  
  .logo {
    height: 40px;
    width: auto;
  }
  
  .navigation {
    flex: 0 0 auto;
  }
  
  .nav-list {
    display: flex;
    list-style-type: none;
    margin: 0;
    padding: 0;
  }
  
  .nav-item {
    margin-left: 1.5rem;
  }
  
  .nav-link {
    text-decoration: none;
    color: #0c0c0c;
    font-weight: 500;
    transition: color 0.3s ease;
  }
  
  .nav-link:hover {
    color: #007bff;
  }
  </style>