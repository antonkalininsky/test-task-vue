<template>
    <div class="item-box">
        <div class="id">ID: {{ data.id }}</div>
        <div class="name">{{ data.name }}</div>
    </div>
</template>
<script>
export default {
    name: "ItemBox",
    props: {
        data: {
            Object,
            default: {
                id: -1,
                name: 'noname'
            }
        }
    }
};
</script>
<style scoped>
.item-box {
    width: 60px;
    height: 60px;
    margin: 5px;

    border: 2px solid black;
    cursor: pointer;

    user-select: none;
}
</style>
