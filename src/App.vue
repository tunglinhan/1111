<template>
  <div id="nav">
    <router-link to="/">HOME</router-link> |
    <router-link to="/example2">YOYO-BALL</router-link> |
    <router-link to="/example3">BADMINTON</router-link> |
    <router-link to="/home">SKATEBOARD</router-link> |
    <router-link to="/example4">BOXING</router-link>
  </div>
  <router-view/>
</template>

<style>
#app {
  background: #0439D9;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  background: #0439D9;
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #021E73;
}

#nav a.router-link-exact-active {
  color: #BDF2E3;
}
</style>
