<script setup>
import Inventory from './components/Inventroy/Inventory.vue';
import Skeleton from './components/UI/Skeleton.vue';
import CloseButton from './components/UI/CloseButton.vue';

</script>

<template>
  <main>
    <div class="container">
      <div class="flex">
        <div class="left_bar">
          <img style="margin-bottom: 20px;" src="./assets/img/blur.png">
          <Skeleton style="margin-bottom: 24px;" width="100%" height="24px" borderRadius="8px" />
          <Skeleton style="margin-bottom: 16px;" width="155px" height="10px" borderRadius="4px" />
          <Skeleton style="margin-bottom: 16px;" width="190px" height="10px" borderRadius="4px" />
          <Skeleton style="margin-bottom: 16px;" width="170px" height="10px" borderRadius="4px" />
          <Skeleton style="margin-bottom: 24px;" width="160px" height="10px" borderRadius="4px" />
          <Skeleton width="80px" height="10px" borderRadius="4px" />
        </div>
        <Inventory />
      </div>
      <div class="bottom_bar">

        <Skeleton width="100%" height="36px" borderRadius="12px" />
        <CloseButton class="close_button" />

      </div>
    </div>
  </main>
</template>

<style lang="scss" scoped>
.flex {
  display: flex;
  flex-direction: row;
  gap: 24px;
}

.bottom_bar {
  border-radius: 12px;
  padding: 18px 68px 18px 18px;
  align-items: center;
  display: flex;
  width: 100%;
  border: 1px solid #4D4D4D;
  background: #262626;
  box-sizing: border-box;
  margin-top: 24px;
  position: relative;
  .close_button{
    position: absolute;
    top: 6px;
    right: 6px;
  }
}

.left_bar {
  border-radius: 12px;
  padding: 18px 14px 24px 14px;
  flex-direction: column;
  align-items: center;
  display: flex;
  width: 236px;
  border: 1px solid #4D4D4D;
  background: #262626;

  img {
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
    max-width: 797px;
  }
}
</style>
