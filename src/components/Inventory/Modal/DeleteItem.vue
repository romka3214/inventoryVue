<template>
    <div class="deleteForm">
        <Input style="margin-bottom: 20px;" v-model.number="input" onkeyup="this.value = this.value.replace('/^\d+$/','');" />
        <div class="flex">
            <Button @click="emit('closeDeleteItemPopUp');">
                Отмена
            </Button>
            <ButtonRed @click="submit">
                Подтвердить
            </ButtonRed>
        </div>
    </div>
</template>
<script setup>
import ButtonRed from './../../UI/ButtonRed.vue';
import Button from './../../UI/Button.vue';
import Input from './../../UI/Input.vue';
import { ref } from 'vue';

const emit = defineEmits(['closeDeleteItemPopUp', 'changeQuantity'])

const input = ref(null);

const validate = (event) =>{
    console.log(event);
}

const submit = () => {
    if (input.value > 0) {
        emit('changeQuantity', input.value);
        emit('closeDeleteItemPopUp');
    }
    
}

</script>
<style lang="scss">
.flex {
    width: 100%;
    display: flex;
    flex-wrap: nowrap;
    gap: 10px;
    box-sizing: border-box;
}

.deleteForm {
    position: absolute;
    bottom: 0;
    right: 0;
    z-index: 100;
    width: 100%;
    padding: 20px;
    margin: 0 auto;
    backdrop-filter: blur(6px);
    border: 1px solid #4D4D4D;
    background: rgba(38, 38, 38, 0.60);
    box-sizing: border-box;


}
</style>