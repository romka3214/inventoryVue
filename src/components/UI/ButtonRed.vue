<template>
    <button class="btn_red">
        <slot />
    </button>
</template>
<script setup>


</script>
<style lang="scss">
    .btn_red{
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 11px 15px;
        font-size: 14px;
        color: #fff;
        border-radius: 8px;
        outline: none;
        border: none;
        background-color: #FA7272;
        cursor: pointer;
        transition: .2s ease-in;
        &:hover{
            background-color: #ff5454;
        }
    }
</style>