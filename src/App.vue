<template>
  <div id="app">
    <SimpleCalculator />
  </div>
</template>

<script>
import SimpleCalculator from './components/SimpleCalculator.vue';

export default {
  components: {
    SimpleCalculator,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background-color: #fafafa;
}
</style>

