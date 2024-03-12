<template>
  <div>
    <h2>Register</h2>
    <form @submit.prevent="register">
      <label for="username">Username:</label>
      <input type="text" v-model="username" required>

      <label for="password">Password:</label>
      <input type="password" v-model="password" required>

      <button type="submit">Register</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: ''
    };
  },
  methods: {
    async register() {
      try {
        // Send registration data to the server
        const response = await fetch('http://localhost:8765/register', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({
            username: this.username,
            password: this.password
          })
        });

        if (response.ok) {
          // Registration successful
          console.log('User registered successfully');
        } else {
          // Registration failed
          const errorData = await response.json();
          console.error('Registration failed:', errorData.error);
        }
      } catch (error) {
        console.error('Error during registration:', error);
      }
    }
  }
};
</script>

<style scoped>
/* Add your component-specific styles here */
</style>
