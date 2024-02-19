<script setup>
  import HeaderComponent from './components/HeaderComponent.vue'
  import HeroBannerComponent from './components/HeroBannerComponent.vue'
  import NoticeComponent from './components/NoticeComponent.vue'
  import FormComponent from './components/FormComponent.vue'
  import AttributionComponent from './components/AttributionComponent.vue'
</script>

<template>
  <main class="main">
    <HeaderComponent/>
    <HeroBannerComponent/>
    <NoticeComponent/>
    <FormComponent/>
    <AttributionComponent/>
  </main>

</template>

<style>
  @import './scss/var.scss';
</style>