<template>
  <div id="app">
    <header>
      <nav-bar />
    </header>
    <nuxt />
  </div>
</template>
<script>
import NavBar from '~/components/NavBar.vue'
export default {
  components: {
    NavBar
  }
}
</script>
