<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <hr>
    <p>Number: {{ num }}</p>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String,
    num: {
      type: Number,
      default: 100,
      validator: function (value) {
        return value == parseInt(value)
          && value >= 0
          && value <= 100
      }
    }
  },
  data: function() {
    return {
      message: 'バリデーションチェック',
    }
  }

}
</script>

<style>
</style>
