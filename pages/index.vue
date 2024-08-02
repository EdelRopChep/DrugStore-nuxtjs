<script>
import Header from '~/components/Header.vue';
import Footer from '~/components/Footer.vue';
export default{
    components:{
        Header,
        Footer
    },

    name: 'HomePage',
  data() {
    return {
      activeForm: 'admin',
      admin: {
        username: '',
        password: ''
      },
      user: {
        name: '',
        email: '',
        password: ''
      },
      pharmacist: {
        name: '',
        email: '',
        license: '',
        password: ''
      }
    }
  },
  methods: {
    submitAdminLogin() {
      console.log('Admin login submitted:', this.admin)
      // Add your login logic here
    },
    submitUserRegister() {
      console.log('User registration submitted:', this.user)
      // Add your registration logic here
    },
    submitPharmacistRegister() {
      console.log('Pharmacist registration submitted:', this.pharmacist)
      // Add your registration logic here
    }
  }
}
</script>
<template>
    <Header/>
    
    


    <div class="home-container">
    <div class="image-section">
      <img src="~/assets/home.jpeg" alt="Pharmacy Image" class="pharmacy-image">
    </div>
    <div class="form-section">
      <h1 class="welcome-text">Welcome to Our Drug Store</h1>
      <div class="form-container">
        <div class="form-tabs">
          <button @click="activeForm = 'admin'" :class="{ active: activeForm === 'admin' }">Admin Login</button>
          <button @click="activeForm = 'user'" :class="{ active: activeForm === 'user' }">User Register</button>
          <button @click="activeForm = 'pharmacist'" :class="{ active: activeForm === 'pharmacist' }">Pharmacist Register</button>
        </div>
        
        <form v-if="activeForm === 'admin'" @submit.prevent="submitAdminLogin" class="form">
          <h2>Admin Login</h2>
          <input v-model="admin.username" type="text" placeholder="Username" required>
          <input v-model="admin.password" type="password" placeholder="Password" required>
          <button type="submit">Login</button>
        </form>

        <form v-if="activeForm === 'user'" @submit.prevent="submitUserRegister" class="form">
          <h2>User Registration</h2>
          <input v-model="user.name" type="text" placeholder="Full Name" required>
          <input v-model="user.email" type="email" placeholder="Email" required>
          <input v-model="user.password" type="password" placeholder="Password" required>
          <button type="submit">Register</button>
        </form>

        <form v-if="activeForm === 'pharmacist'" @submit.prevent="submitPharmacistRegister" class="form">
          <h2>Pharmacist Registration</h2>
          <input v-model="pharmacist.name" type="text" placeholder="Full Name" required>
          <input v-model="pharmacist.email" type="email" placeholder="Email" required>
          <input v-model="pharmacist.license" type="text" placeholder="License Number" required>
          <input v-model="pharmacist.password" type="password" placeholder="Password" required>
          <button type="submit">Register</button>
        </form>
      </div>
    </div>
  </div>


    <Footer/>
</template>

<style scoped>
.home-container {
  display: flex;
  height: 100vh;
}

.image-section, .form-section {
  flex: 1;
}

.image-section {
  background-color: #f0f0f0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.pharmacy-image {
  max-width: 100%;
  max-height: 100%;
  object-fit: cover;
}

.form-section {
  padding: 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.welcome-text {
  text-align: center;
  margin-bottom: 2rem;
}

.form-container {
  max-width: 400px;
  margin: 0 auto;
}

.form-tabs {
  display: flex;
  margin-bottom: 1rem;
}

.form-tabs button {
  flex: 1;
  padding: 0.5rem;
  background-color: #f0f0f0;
  border: none;
  cursor: pointer;
}

.form-tabs button.active {
  background-color: #007bff;
  color: white;
}

.form {
  display: flex;
  flex-direction: column;
}

.form input {
  margin-bottom: 1rem;
  padding: 0.5rem;
}

.form button {
  padding: 0.5rem;
  background-color: #007bff;
  color: white;
  border: none;
  cursor: pointer;
}

.form button:hover {
  background-color: #0056b3;
}
</style>