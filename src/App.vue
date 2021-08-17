<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="less">
html,
body {
  padding: 0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  width: 100%;
}

#nav {
  line-height: 40px;
  background-color: #212a4c;
  padding: 10px;
  a {
    font-weight: bold;
    text-decoration: none;
    color: #bac2d0;
    margin-right: 30px;

    &.router-link-exact-active {
      color: #fff;
    }
  }
}
</style>
