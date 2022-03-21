<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>|
    <router-link :to ="{name : 'jobs'}">Jobs</router-link>
    
  </nav>
  <button @click="Redirect">Redirect</button>
  <button @click="back">Go back</button>
  <button @click="forward">Go forward</button>
  
  <router-view/>
</template>

<script>
export default {
  methods: {
    Redirect ()
    {
      this.$router.push({name : 'home'})

    },
    back (){
      this.$router.go(-1)
    },
    forward ()
    {
      this.$router.go(1)

    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body { background:#d6eaff}
nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding:10px;
  border-radius:10px; 
}

nav a.router-link-exact-active {
  color: white;
  background: rgb(220, 20, 170);
}
button {
  margin:0  10px;
  padding:10px;
  border: none;
  border-radius:10px;
  background-color:#1e8af7;
  color: white;
  font-weight: bold;
  cursor: pointer;
  
}
</style>
