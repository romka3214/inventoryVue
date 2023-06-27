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
import Modal from './Modal/Modal.vue';
import { ref, watch, onMounted } from 'vue';


const items = ref([]);
onMounted(() => {
  if (localStorage.getItem('items')) {
    try {
      items.value = JSON.parse(localStorage.getItem('items'));
    } catch (e) {
      localStorage.removeItem('items');
      items.value = [
        {
          id: 1,
          name: 'Предмет1',
          description: 'Lorem Ipsum - это текст-"рыба", часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной "рыбой" для текстов на латинице с начала XVI века. В то время некий безымянный печатник создал большую коллекцию размеров и форм шрифтов, используя Lorem Ipsum для распечатки образцов. Lorem Ipsum не только успешно пережил без заметных изменений пять веков, но и перешагнул в электронный дизайн. Его популяризации в новое время послужили публикация листов Letraset с образцами Lorem Ipsum в 60-х годах и, в более недавнее время, программы электронной вёрстки типа Aldus PageMaker, в шаблонах которых используется Lorem Ipsum.',
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
      ];
    }
  } else {
    items.value = [
      {
        id: 1,
        name: 'Предмет1',
        description: 'Lorem Ipsum - это текст-"рыба", часто используемый в печати и вэб-дизайне. Lorem Ipsum является стандартной "рыбой" для текстов на латинице с начала XVI века. В то время некий безымянный печатник создал большую коллекцию размеров и форм шрифтов, используя Lorem Ipsum для распечатки образцов. Lorem Ipsum не только успешно пережил без заметных изменений пять веков, но и перешагнул в электронный дизайн. Его популяризации в новое время послужили публикация листов Letraset с образцами Lorem Ipsum в 60-х годах и, в более недавнее время, программы электронной вёрстки типа Aldus PageMaker, в шаблонах которых используется Lorem Ipsum.',
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
    ];
  }
})


const updateLocalStorage = () => {
  const parsed = JSON.stringify(items.value);
  localStorage.setItem('items', parsed);
  console.log('сохраняем...');
}






const modalState = ref(false)
const modalItem = ref(null)


function openModal(item) {
  modalState.value = true
  modalItem.value = item;
}
function closeModal() {
  modalState.value = false
}

function changeQuantity(item, number) {
  let itemFind = items.value.findIndex((i) => i.id === item.id)
  items.value[itemFind].count = items.value[itemFind].count - number;
  updateLocalStorage();
}

function moveItem(currItemID, placeToMountID) {
  [items.value[currItemID], items.value[placeToMountID]] = [items.value[placeToMountID], items.value[currItemID]];
  updateLocalStorage();
}

</script>

<style lang="scss">
.slide-enter-active .modal,
.slide-leave-active .modal {
  transition: .5s ease-in-out;
}

.slide-enter-from .modal,
.slide-leave-to .modal {
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