<template>
  <div id="app">
    <h1>Calculator</h1>
    <!-- Use the AppCalculator component -->
    <AppCalculator />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import AppCalculator from './components/AppCalculator.vue'; // Import the AppCalculator component

export default defineComponent({
  name: 'App',
 
  components: {
    AppCalculator, // Register the AppCalculator component
  },
});
</script>

<style scoped>
html,body{
  height: 100%;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
#app {
  display: flex;
  flex-direction: column;
  display: flex;
  justify-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
   -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
  background: none;
  padding: 20px;
  border: 2px solid #2baaff;
  border-radius: 10px;
  width: 500px;
}

h1 {
  font-family: Arial, sans-serif;
  color: #2baaff;
  margin: 30px;
}
</style>