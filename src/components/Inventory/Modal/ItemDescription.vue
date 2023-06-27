<template>
    <div class="item_description">
        <div class="name">{{ item.name }}</div>
        <div class="description">{{ item.description }}</div>
    </div>
</template>
<script setup>
const props = defineProps({
    item: Object,
})
await new Promise((res) => setTimeout(res, 1000)); //очень долгий запрос к бд)
</script>
<style scoped lang="scss">

/*
 *  STYLE 1
 */

::-webkit-scrollbar-track
{
	-webkit-box-shadow: inset 0 0 6px #2b2727;
	border-radius: 10px;
	background-color: #202020;
}

::-webkit-scrollbar
{
	width: 12px;
	background-color: #262626;
}

::-webkit-scrollbar-thumb
{
	border-radius: 10px;
	-webkit-box-shadow: inset 0 0 6px #262626;
	background-color: #575757;
}

.item_description {
    overflow-y: scroll;
    max-height: 200px;

    .name {
        text-align: center;
        margin-bottom: 25px;
        font-size: 26px;
    }

    .description {
        text-align: center;
        margin-bottom: 25px;
    }
}
</style>