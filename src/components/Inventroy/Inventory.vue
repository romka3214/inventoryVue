<template>
  <div class="inventory_main">
    <Cell @openModal="openModal" @movedItem="moveItem" v-for="(item, index) in items" :item="item" :key="index"
      :index="index" />

    <Transition duration="500" name="slide">
      <Modal @changeQuantity="changeQuantity" v-if="modalState" :item="modalItem" @closeModal="closeModal" />
    </Transition>

  </div>
</template>
<script setup>
import Cell from './Cell.vue';
import Modal from './Modal.vue';
import { ref } from 'vue';


const items = ref([
  {
    id: 1,
    name: 'Предмет1',
    description: 'Описание',
    ico: '/src/assets/img/ico1.png',
    count: 9,
  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {
    id: 3,
    name: 'Предмет3',
    description: 'Описание',
    ico: '/src/assets/img/ico3.png',
    count: 9,
  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {
    id: 2,
    name: 'Предмет2',
    description: 'Описание',
    ico: '/src/assets/img/ico2.png',
    count: 9,
  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
  {

  },
])
const modalState = ref(false)
const modalItem = ref(null)


function openModal(item) {
  modalState.value = true
  modalItem.value = item;
}
function closeModal() {
  modalState.value = false
}

function changeQuantity(item, number){
  let itemFind = items.value.findIndex((i) => i.id === item.id)
  items.value[itemFind].count = items.value[itemFind].count - number;
  // itemFind.value.count = itemFind.value.count - number;
}

function moveItem(currItemID, placeToMountID) {
  [items.value[currItemID], items.value[placeToMountID]] = [items.value[placeToMountID], items.value[currItemID]];

  // console.log(items.value[$placeToMountID]);
  // let item = items.value[$currItemID];
  // items.value[$placeToMountID] = items.value[$currItemID].item;
  // items.value[$currItemID].item = undefined;
  // items.value.find(item => item.id == $placeToMountID);
}

</script>
<style lang="scss">
.slide-enter-active .modal,
.slide-leave-active .modal{
  transition: .5s ease-in-out;
}

.slide-enter-from .modal,
.slide-leave-to .modal{
  right: -250px;
}
.inventory_main {
  overflow: hidden;
  border-radius: 12px;
  border: 1px solid #4D4D4D;
  background: #262626;
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  position: relative;
}
</style>