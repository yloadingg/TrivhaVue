
<template>
  <div class="container">
 
    <!-- Large Header -->
    <div class="large-header">
  
      <img src="/images/medium-trivha.png" alt="Large Header Image" />
    </div>

    <!-- Sign Up Form -->
    <form @submit.prevent="handleSubmit" class="login-form">
      <input type="email" v-model="email" placeholder="Email" required />
      <input type="text" v-model="username" placeholder="Username" required />

      <div class="password-container">
        <input
          :type="showPassword ? 'text' : 'password'"
          v-model="password"
          id="password"
          placeholder="Password"
          required
        />
        <button
          type="button"
          @click="togglePassword"
          class="toggle-btn"
        >
          {{ showPassword ? '🙈' : '👁️' }}
        </button>
      </div>

      <button type="submit" class="sign-up-btn">Sign up</button>
      <p class="login-link">
        Already have an account? <a href="login">Login</a>
      </p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: '',
      username: '',
      password: '',
      showPassword: false,
    };
  },
  methods: {
    togglePassword() {
      this.showPassword = !this.showPassword;
    },
    handleSubmit() {
      // Handle form submission logic here
      console.log('Form submitted with:', {
        email: this.email,
        username: this.username,
        password: this.password,
      });
    },
  },
};
</script>

<style scoped>
/* src/assets/styles.css */

.container {
    text-align: center;
    background-color: rgba(255, 255, 255, 0.1);
    padding: 40px;
    border-radius: 15px;
    position: relative;
    filter: drop-shadow(1px 1px 4px rgb(151, 150, 151));
    margin: 8em auto; 
    max-width: 1000px; 
    width: 100%; 
    
 
  
}

.large-header {
    display: inline-block;
    text-align: center;
    padding: 10px;
}

.header h1 {
    font-size: 3rem; 
    color: rgb(36, 92, 22);
    text-shadow: 4px 4px 0px #e7e7e7;
    margin-bottom: 20px;
}

.login-form {
    background-color: #e2d4e2;
    padding: 20px;
    border-radius: 10px;
}

.login-form input {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border-radius: 5px;
    border: 1px solid #ddd;
    font-size: 16px;
}

.sign-up-btn {
    width: 100%;
    padding: 10px;
    background-color: #28a745;
    color: white;
    font-size: 16px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.sign-up-btn:hover {
    background-color: #218838;
}

.login-link {
    margin-top: 10px;
    font-size: 14px;
    color:black;
}

.login-link a {
    color: #007bff;
    text-decoration: none;
}

/* Modal Styles */
.modal {
    display: flex; /* Center modal */
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    justify-content: center;
    align-items: center;
    animation: fadeIn 0.3s ease-out;
}

.modal-content {
    background-color: #f1f1f1;
    padding: 20px;
    border-radius: 10px;
    width: 90%; /* Responsive modal width */
    max-width: 500px;
    text-align: center;
    transform: scale(0);
    animation: zoomIn 0.3s ease-out forwards;
}

/* Animations */
@keyframes zoomIn {
    from {
        transform: scale(0);
    }
    to {
        transform: scale(1);
    }
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

.open-modal-btn,
.close-modal-btn {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1rem;
}

.open-modal-btn:hover,
.close-modal-btn:hover {
    background-color: #0056b3;
}

</style>
