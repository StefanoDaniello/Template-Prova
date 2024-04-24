<template>
  <HeaderComponent/>
  <MainComponents/>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponents from './components/MainComponents.vue'
  export default {
    name: 'App',
    components: {
      HeaderComponent,
      MainComponents
    }
  }
</script>

<style lang="scss" scoped>
  
</style>