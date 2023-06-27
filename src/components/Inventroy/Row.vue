<script setup>
import Cell from './Cell.vue';
const props = defineProps({
    items: Array,
})
</script>

<template>
    <div v-for="item in items">
        <Cell :item="item"/>
    </div>
</template>

<style lang="scss">
.inventory_cell {
    border-bottom: 1px solid #4D4D4D;
    border-right: 1px solid #4D4D4D;
    height: 100px;
    width: 100px;
    color: #4D4D4D;

    &:nth-child(5n) {
        border-right: none;
    }

    &:nth-child(n + 20) {
        border-bottom: none;
    }
}
</style>