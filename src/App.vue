<template>
  <CreatePost />
  <MainLayout />
</template>

<script>
  import CreatePost from './components/CreatePost.vue'
  import MainLayout from './layouts/MainLayout.vue'

  import './assets/tailwind.css'
  export default{
    name: 'App',
    components: {
      CreatePost,
      MainLayout,
    },
  }
</script>

<style src="./assets/tailwind.css"/>
