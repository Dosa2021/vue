<template>
  <!-- <router-view></router-view> -->
  <section>
  <h1>{{ title }}</h1>
    <p>{{message}}</p>
    <hr>
    <pre>{{ now }}</pre>
    <nuxt-link to="/other">go other</nuxt-link>
  </section>
</template>

<script>
export default {
  data: function() {
    return {
      title: 'Hello',
      message: 'this is message',
      now: 'wait...'

    }
  },
  created: function() {
    setInterval(() => {
      var d = new Date()
      this.now = d.getHours()
        + ':' + d.getMinutes()
        + ':' + d.getSeconds()
    })
  }
}
</script>
