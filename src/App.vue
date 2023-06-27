<script setup>
import Inventory from './components/Inventroy/Inventory.vue';


</script>

<template>
  <main>
    <div class="container">
      <Inventory />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #0f0f0f;

  .container {
    max-width: 80%;
  }
}
</style>
