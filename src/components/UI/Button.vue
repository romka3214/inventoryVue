<template>
    <button class="btn">
        <slot />
    </button>
</template>
<script>

</script>
<style lang="scss">
    .btn{
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 11px 15px;
        font-size: 14px;
        color: #2D2D2D;
        border-radius: 8px;
        outline: none;
        border: none;
        background-color: #fff;
        cursor: pointer;
        transition: .2s ease-in;
        &:hover{
            background-color: #ff5454;
        }
    }
</style>