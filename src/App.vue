<template>
  <div id="app">
    <div class="header"></div>
    <Todo />
  </div>
</template>

<script>
import Todo from './components/Todo.vue'

export default {
  components: { Todo },
  name: 'App',
}
</script>

<style lang="sass">
#app
  font-family: 'Josefin Sans', sans-serif
  background-color: hsl(0, 0%, 98%)
  .header
    background: url(./assets/bg-desktop-light.jpg), hsl(0, 0%, 98%)
    height: 200px
    background-repeat: no-repeat
    background-size: cover
    width: 100vw
</style>
