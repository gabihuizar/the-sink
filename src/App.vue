<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Hogar</router-link> |
      <router-link to="/quehaceres">Que Haceres</router-link>
    </div>
    <router-view />
  </div>
</template>

<style lang="scss" scoped>
@import './src/assets/colors.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: $cornflower;
  background-color: $dark-purple-grey;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: $cornflower;
}

#nav a.router-link-exact-active {
  color: $sky-blue-green;
}
</style>
