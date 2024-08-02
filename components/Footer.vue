<!-- components/Footer.vue -->
<template>
    <footer class="footer">
      <div class="footer-content">
        <div class="copyright">
          &copy; {{ currentYear }} Your Drug Store. All rights reserved.
        </div>
        <nav class="footer-nav">
          <NuxtLink to="/privacy" class="footer-link">Privacy Policy</NuxtLink>
          <NuxtLink to="/terms" class="footer-link">Terms of Service</NuxtLink>
          <NuxtLink to="/contact" class="footer-link">Contact Us</NuxtLink>
        </nav>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'Footer',
    computed: {
      currentYear() {
        return new Date().getFullYear()
      }
    }
  }
  </script>
  
  <style scoped>
  .footer {
    background-color: #7d0f6a;
    padding: 1rem 0;
    margin-top: 2rem;
  }
  
  .footer-content {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 1rem;
  }
  
  .copyright {
    font-size: 0.9rem;
    color: #bede09;
  }
  
  .footer-nav {
    display: flex;
    gap: 1rem;
  }
  
  .footer-link {
    color: #9bb41c;
    text-decoration: none;
    font-size: 0.9rem;
    transition: color 0.3s ease;
  }
  
  .footer-link:hover {
    color: #007bff;
  }
  
  @media (max-width: 768px) {
    .footer-content {
      flex-direction: column;
      text-align: center;
    }
  
    .footer-nav {
      margin-top: 1rem;
    }
  }
  </style>