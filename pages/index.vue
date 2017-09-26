<template>
  <section class="container">
    <h1 class="title">Trends</h1>
    {{ data }}
  </section>
</template>

<script>
require('isomorphic-fetch');
import Trends from '~/components/trends.vue'

export default {
  components: {
    Trends
  },
  asyncData (opts) {
    return fetch("http://localhost:1337")
      .then((res) => res.json())
      .then((trends) => ({ ...trends }))
  }
}
</script>

<style>
body {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
}

.container {
  padding: 50px;
}

.title {
  display: block;
  font-weight: 300;
  font-size: 48px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>
