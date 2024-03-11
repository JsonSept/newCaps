<template>
  <div>
    <h1>This is the signup page</h1>
  </div>

  <div class="form-container">
        <h2>Signup</h2>
        <form action="/about" method="post">
            <div class="form-group">
                <label for="name">Name:</label>
                <input type="text" id="name" name="username" placeholder="Enter your name" required autocomplete="off">
            </div>
            <div class="form-group">
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" placeholder="password" required>
            </div>
            <button type="submit" class="submit-btn" @click="registerUser()">SignUp</button>
            
        </form>
    </div>

  <!-- <div>
    <input type="text" name="username" placeholder="username" v-model="username"><br><br>
    <input type="text" name="password" placeholder="password" v-model="password"><br><br>
    <button @click='registerUser()'>SignUp</button>
  </div> -->

<!-- <router-link to="user"><button>Signup</button></router-link> -->
</template>


<script>
export default {
  data(){
    return {
      username:null,
      password:null
    }
  },
  computed: {
    registerUser(){
      this.$Store.dispatch("registerUser",this.$data)
    }
  }
}

</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

h2 {
    text-align: center;
    margin-bottom: 30px;
}

.form-container {
    width: 300px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.form-group {
    margin-bottom: 15px;
}

.form-group label {
    display: block;
    font-weight: bold;
    margin-bottom: 5px;
}

.form-group input {
    width: 100%;
    padding: 8px;
    font-size: 10px;
    border: 1px solid;
    border-radius: 3px;
}

.submit-btn {
    display: block;
    width: 100%;
    padding: 10px;
    background-color: #472dbb;
    border: none;
    cursor: pointer;
}

.submit-btn:hover {
    background-color: #4565a0;
}
p {
    margin-top: 15px;
}
</style>