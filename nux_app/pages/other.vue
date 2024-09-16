<template>
  <section>
  <h1>{{ title }}</h1>
    <p>{{message}}</p>
    <hr>
  </section>
</template>

<script>
export default {
  data: function() {
    return {
      title: 'Other',
      message: 'this is Other',

    }
  }
}
</script>
