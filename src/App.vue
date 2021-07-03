<template>
  <div class="app">
    <div class="nav">
      <router-link to="/">Spacer</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;800&display=swap');

* {
  box-sizing: border-box;
}

body {
  font-family: Montserrat, sans-serif;
}
</style>
