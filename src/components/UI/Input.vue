<template>
    <input :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" required class="input" type="number"
        placeholder="Введите количество">
</template>
<script setup>
defineProps({
    modelValue: {
        type: Number,
    }
});

</script>
<style lang="scss">
.input {
    border-radius: 4px;
    border: 1px solid #4D4D4D;
    background: #262626;
    outline: none;
    padding: 12px;
    width: 100%;
    box-sizing: border-box;
    color: #fff;

    &::placeholder {
        font-size: 14px;
        color: #fff;
    }

    &::-webkit-outer-spin-button,
    &::-webkit-inner-spin-button {
        -webkit-appearance: none;
        margin: 0;
    }

    & {
        -moz-appearance: textfield;
    }
}
</style>