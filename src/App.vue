<script setup>
import CardContainer from "@/components/CardContainer.vue";
import ButtonsContainer from "@/components/ButtonsContainer.vue";
import NavBar from "@/components/NavBar.vue";
</script>

<template>

  <div class="container">
    <CardContainer/>
    <ButtonsContainer/>
  </div>

  <NavBar/>

</template>

<style scoped>
  .container {
    position: relative;
    width: 300px;
    height: 500px;
    background-color: white;
    border-radius: 20px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    /*overflow: hidden;*/
  }
</style>
