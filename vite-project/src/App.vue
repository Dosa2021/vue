<template>
  <div class="tab">
    <button v-bind:class="{ 'item--active': isCurrent == 1}" v-on:click="changeTab(1)">TAB A</button>
    <button v-bind:class="{ 'item--active': isCurrent == 2}" v-on:click="changeTab(2)">TAB B</button>
    <button v-on:click="changeTab(3)">TAB C</button>
    <div v-show="isCurrent === 1">
      <p>SECTION A</p>
      <input type="text" v-model="hoge.name">
      <input type="text" v-model="hoge.mail">
    </div>
    <div v-show="isCurrent === 2">
      <p>SECTION B</p>
      <input type="text" v-model="hoge.password">
    </div>
    <div v-show="isCurrent === 3">
      <p>SECTION C</p>
    </div>
    <div>{{ data.name }}</div>
  </div>



</template>


<script setup>
import { ref, toRaw } from 'vue'
import { getCurrentInstance } from 'vue';

let data = {
  name: 'taro',
  mail: 'aaa@gmail.com',
  password: 'password'
}
console.log('d-----------')
console.log(data)

let copyLists = structuredClone(data)
let hoge = ref(data)

let url_string = window.location.href;
let url = new URL(url_string);
let dataUrl=url.searchParams.get("tab");
console.log('d-2222----------')
console.log(dataUrl)

let page = dataUrl ? dataUrl : 1; 

console.log(typeof dataUrl)

let isCurrent = ref(Number(page))
console.log('isCurrent----------')
console.log(isCurrent.value)
const changeTab = function (number) {
  location.reload()
  window.location.href = '/?tab=' + number
  this.isCurrent = number
};
const initHoge = function (number) {
  // hoge = ref(rawCount)
}

</script>



<style scoped>
.item--active {
  background-color: red;
}
</style>
