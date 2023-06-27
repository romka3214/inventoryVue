<template>
    <div class="item_description">
        <div class="name">{{ item.name }}</div>
        <div class="description">{{ item.description }}</div>
    </div>
</template>
<script setup>
const props = defineProps({
    item: Object,
})
await new Promise((res) => setTimeout(res, 2000)); //очень долгий запрос к бд)
</script>
<style scoped lang="scss">
.item_description {
    overflow: scroll;
    max-height: 200px;

    .name {
        text-align: center;
        margin-bottom: 25px;
        font-size: 26px;
    }

    .description {
        text-align: center;
        margin-bottom: 25px;
    }
}
</style>