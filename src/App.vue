<template>
  <div class="container">
    <nav class="navbar navbar-expand-lg">
      <div class="container-fluid">
        <router-link 
          class="navbar-brand" 
          :to="{name: 'main'}"
          >Portal</router-link>
          <ul class="nav">
    <li class="nav-item">
      <router-link class="nav-link" :to="{name: 'login'}">
        Вход
      </router-link>
    </li>
    <li class="nav-item">
      <router-link class="nav-link" :to="{name: 'register'}">
        Регистрация</router-link>
    </li>
  </ul>
      </div>
    </nav>
  </div>
  
  <div class="container">
    <router-view />
  </div>
  
</template>

<script>
  export default {

  }
</script>
 
<style scoped>
  .container {
    background-color: rgba(255, 255, 255, 0.132);
    height: auto;
  }
  .navbar-brand {
    color: white;
  }
</style>
