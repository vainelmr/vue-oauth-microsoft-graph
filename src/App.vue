<template>
  <div>
    <BaseLayout>
    <HomePage />
    <BaseButton>
      Base button with custom margin
    </BaseButton>
    <BaseButton disabled>
      Base Button disabled
    </BaseButton>
    </BaseLayout>
  </div>
</template>

<script>
import HomePage from './pages/HomePage.vue';
import BaseLayout from './components/BaseLayout.vue';
import BaseButton from './components/BaseButton.vue';

export default {
  name: 'App',
  components: {
    BaseButton,
    HomePage,
    BaseLayout
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
