<template>
    <div class="modal_back">
        <div class="exit_modal" @click="close"></div>

        <div class="modal">
            <img :src=item.ico>
            <div class="decoration_line"></div>
            <Suspense>
                <ItemDescription :item="item" />
                <template #fallback>
                    <ItemDescriptionSkeleton />
                </template>
            </Suspense>


            <div class="decoration_line"></div>
            <ButtonRed class="deleteButton" style="vertical-align:bottom;" @click="showDeleteItemPopUp">
                Удалить предмет
            </ButtonRed>
            <Transition duration="500" name="slideToTop">
                <DeleteItem @closeDeleteItemPopUp="closeDeleteItemPopUp" @changeQuantity="changeQuantity"
                    v-if="deleteItemPopUp" />
            </Transition>



            <CloseButton class="close_button" @click="close" />
        </div>


    </div>
</template>

<script setup>
import CloseButton from './../../UI/CloseButton.vue';
import ButtonRed from './../../UI/ButtonRed.vue';
import DeleteItem from './DeleteItem.vue';
import ItemDescription from './ItemDescription.vue';
import ItemDescriptionSkeleton from './ItemDescriptionSkeleton.vue';
import { ref } from 'vue';




const emit = defineEmits(['closeModal', 'changeQuantity'])

const props = defineProps({
    item: Object,
})

const deleteItemPopUp = ref(false);

const showDeleteItemPopUp = () => {
    deleteItemPopUp.value = true;
}
const closeDeleteItemPopUp = () => {
    deleteItemPopUp.value = false;
}
const changeQuantity = (number) => {
    emit('changeQuantity', props.item, number);
    if(props.item.count <= number){
        close();
    }
    
}



const close = () => {
    emit('closeModal');
}
</script>

<style lang="scss">
.slideToTop-enter-active,
.slideToTop-leave-active {
    transition: .5s ease-in-out;
}

.slideToTop-enter-from,
.slideToTop-leave-to {
    bottom: -143px;
}

.exit_modal {
    z-index: 90;
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.modal_back {
    width: 100%;
    height: 100%;

    .modal {
        padding: 50px 15px 18px;
        z-index: 99;
        backdrop-filter: blur(6px);
        background: rgba(38, 38, 38, 0.50);
        position: absolute;
        top: 0;
        right: 0;
        height: 100%;
        width: 250px;
        border-left: 1px solid #4D4D4D;
        color: #fff;
        box-sizing: border-box;

        img {
            width: 130px;
            height: 130px;
            display: block;
            margin: 0 auto;
            margin-bottom: 30px;
        }

        .close_button {
            position: absolute;
            top: 8px;
            right: 8px;
        }

        .decoration_line {
            width: 100%;
            height: 1px;
            margin-bottom: 15px;
            background: #4D4D4D;
        }

        .deleteButton {
            position: absolute;
            bottom: 20px;
            width: calc(100% - 30px);
            z-index: 95;
        }


    }
}
</style>