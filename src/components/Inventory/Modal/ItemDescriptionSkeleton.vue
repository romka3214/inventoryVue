<template>
    <div class="center">
        <Skeleton style="margin-bottom: 24px;" width="100%" height="30px" borderRadius="8px" />
        <Skeleton style="margin-bottom: 16px;" width="100%" height="10px" borderRadius="4px" />
        <Skeleton style="margin-bottom: 16px;" width="100%" height="10px" borderRadius="4px" />
        <Skeleton style="margin-bottom: 16px;" width="100%" height="10px" borderRadius="4px" />
        <Skeleton style="margin-bottom: 16px;" width="180px" height="10px" borderRadius="4px" />
        <Skeleton style="margin-bottom: 24px;" width="80px" height="10px" borderRadius="4px" />
    </div>
</template>
<script setup>
import Skeleton from './../../UI/Skeleton.vue';
</script>
<style scoped lang="scss">
.center{
    display: flex;
    align-items: center;
    flex-direction: column;
}
</style>