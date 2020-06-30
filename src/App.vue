<template>
  <div class="app">
    <!-- <div class="nav">
      <router-link to="/">SpaceXD</router-link>
      <router-link to="/about">about</router-link>
    </div> -->
    <router-view/>
  </div>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700;800&display=swap');

  *{
    box-sizing: border-box;
  }

  body{
    margin: 0;
    padding: 0;
    font-family: 'Montserrat', sans-serif;
  }
</style>
