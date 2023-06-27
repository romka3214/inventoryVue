<script setup>
import Inventory from './components/Inventroy/Inventory.vue';
import Skeleton from './components/UI/Skeleton.vue';


</script>

<template>
  <main>
    <div class="container">
      <div class="flex">
        <div class="left_bar">
        <img src="./assets/img/blur.png">
      </div>
      <Inventory />
      </div>
      <div class="bottom_bar">

        <Skeleton width="100%" height="100%" borderRadius="12px"/>
      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
.flex{
  display: flex;
  flex-direction: row;
  gap: 24px;
}

.bottom_bar{
  border-radius: 12px;
  padding: 18px 68px 18px 18px;
  align-items: center;
  display: flex;
  width: 100%;
  border: 1px solid #4D4D4D; 
  background: #262626;
  box-sizing: border-box;
  margin-top: 24px;
}
.left_bar {
  border-radius: 12px;
  padding: 18px 14px 24px 14px;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  display: flex;
  width: 236px;
  border: 1px solid #4D4D4D; 
  background: #262626; 
  img{
    border-radius: 8px;
    width: 100%;
  }
}

main {
  height: 100vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #0f0f0f;

  .container {
    max-width: 785px;
  }
}
</style>
