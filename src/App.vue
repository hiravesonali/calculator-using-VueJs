<template>
  <div id="app">
    <Calculator/>
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Calculator
  }
}
</script>

<style>
  @import "https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css";
</style>

