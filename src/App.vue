<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue'

let count = ref(0);
console.log(count);

function increment(){
  count.value++;
}

function increment10(){
  count.value = count.value + 10;
}

function decrement(){
  count.value--;
}

function decrement10(){
  count.value = count.value - 10;
}

function reset(){
  count.value=0;
}
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />

    <button @click="decrement()">-</button>
    <button @click="decrement10()">-10</button>
    <span>{{ count }}</span>
    <button @click="increment()">+</button>
    <button @click="increment10()">+10</button>
    <button @click="reset()">reset</button>
    
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
