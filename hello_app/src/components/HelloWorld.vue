<template>
  <div class="hello">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <hr>
    <div>
      <input type="text" v-model="input">
      <button v-on:click="doAction">Click</button>
    </div>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    title: String,
  },
  data: function() {
    return {
      message: 'お名前は？',
      input: 'no name'
    }
  },
  methods: {
    doAction: function() {
      this.message = 'こんにちは,' + this.input + 'さん'
      this.$emit("result-event", this.input);
    }
  }
}
</script>

<style>
</style>
