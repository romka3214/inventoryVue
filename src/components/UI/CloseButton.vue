<template>
    <div class="close_button">
        <svg width="12" height="12" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 1.05L10.95 0L6 4.95L1.05 0L0 1.05L4.95 6L0 10.95L1.05 12L6 7.05L10.95 12L12 10.95L7.05 6L12 1.05Z"
                fill="white" />
        </svg>
    </div>
</template>
<script setup>

</script>
<style scoped lang="scss">
.close_button {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px;
    border-radius: 10px;
    cursor: pointer;
    max-width: fit-content;

    &:hover {
        background-color: #2F2F2F;
    }
}
</style>