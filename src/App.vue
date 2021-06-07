<template>
  <div id="app">
    <div class="header">
      <div>Reliable, efficient delivery</div>
      <div>Powered by Technology</div>
      <div>
        Our Artificial Intelligence powered tools use millions of project data
        <br/>
        points to ensure that your project is successful
      </div>
    </div>
    <Category/>
  </div>
</template>

<script>
import Category from '@/components/Category.vue'

export default {
  name: 'App',
  components: {
    Category
  }
}
</script>

<style>
</style>
