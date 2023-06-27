<script setup>

const props = defineProps({
    item: Object,
    index: Number,
})

const emit = defineEmits(['movedItem', 'openModal'])


const startDrag = (event, id) => {
    event.dataTransfer.dropEffect = 'move';
    event.dataTransfer.effectAllowed = 'move';
    event.dataTransfer.setData('id', id);
    console.log('drag');
}

const onDrop = (event, id) => {
    const itemId = event.dataTransfer.getData('id');
    emit('movedItem', itemId, id);
}

const dragEnter = (e) => {
    e.target.classList.add('over');
}
const dragOver = (e) => {
    e.target.classList.remove('over');
}
const click = () => {
    emit('openModal', props.item)
    console.log(props.item);
}
</script>

<template>
    <div v-if="Object.keys(item).length !== 0" draggable="true" @click="click" @dragstart="startDrag($event, index)"
        class="inventory_cell">
        <img :src=item.ico alt="">
        <div class="count">
            {{ item.count }}
        </div>
    </div>
    <div v-else draggable="false" @drop="onDrop($event, index)" @dragenter.prevent="dragEnter($event)" @dragover.prevent
        @dragleave="dragOver($event)" class="inventory_cell">

    </div>
</template>

<style scoped lang="scss">
.inventory_cell {
    border-bottom: 1px solid #4D4D4D;
    border-right: 1px solid #4D4D4D;
    height: 100px;
    width: 100px;
    color: #4D4D4D;
    overflow: hidden;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;

    &.over {
        background-color: #2F2F2F;
    }

    &[draggable="true"] {
        cursor: pointer;
        img {
            height: 54px;
            width: 54px;
            object-fit: cover;
            pointer-events: none;
        }

        .count {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 5px;
            position: absolute;
            bottom: 0;
            right: 0;
            border-top: 1px solid #4D4D4D;
            border-left: 1px solid #4D4D4D;
            border-radius: 6px 0 0 0;
        }
    }


    &:nth-child(5n) {
        border-right: none;
    }

    &:nth-child(n + 21) {
        border-bottom: none;
    }
}
</style>