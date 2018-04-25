<template>
  <div id="app">
    <img class="cloud-one" src="./assets/cloud1.png" alt="cloudone">
    <img class="cloud-two" src="./assets/cloud2.png" alt="cloudtwo">
    <router-view/>
  </div>
</template>

<style lang="scss">
body {
  background-image: linear-gradient(to bottom, #00c6fb 0%, #005bea 100%);
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
#app {
  position: relative;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  .cloud-one {
    position: fixed;
    top: 40%;
    left: 18%;
  }
  .cloud-two {
    position: fixed;
    top: 30%;
    left: 66%;
  }
}
</style>
