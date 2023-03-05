<template lang="">
    <div class="main">
        <div class="top-panel">
            <div class="items-group-wrap">
                <div class="items-group draw-box">
                    <ItemBox
                        v-for="(item, index) in selectedItems"
                        :key="item.id"
                        :data="item"
                        @click="removeSelectedItems(index)"
                    />
                </div>
                <div class="items-group-text">selected: {{ selectedItems.length }} / {{ selectedItemsLimit }}</div>
            </div>
            <div class="item-show draw-box">
                <div
                    class="item-show-text"
                    v-if="Object.keys(showItem).length !== 0"
                >
                    Selected item: {{ showItem.name }} (id: {{ showItem.id }})
                </div>
                <div class="item-show-text" v-else>No selected item</div>
            </div>
        </div>
        <div class="bot-panel">
            <div class="left-column draw-box">
                <ItemBox
                    v-for="item in leftData"
                    :key="item.id"
                    :data="item"
                    @click="addSelectedItems(item.id)"
                />
            </div>
            <div class="right-column draw-box">
                <ItemBox
                    v-for="item in rightData"
                    :key="item.id"
                    :data="item"
                    @click="setShownItem(item.id)"
                />
            </div>
        </div>
    </div>
</template>

<script>
import ItemBox from "./ItemBox.vue";
import leftData from "./../data/leftData.json";
import rightData from "./../data/rightData.json";

export default {
    name: "MainWindow",
    components: {
        ItemBox,
    },
    data() {
        return {
            leftData,
            rightData,
            showItem: {},
            selectedItems: [],
            selectedItemsLimit: 6,
            fuck: Array()
        };
    },
    methods: {
        addSelectedItems(id) {
            // проверка на количество
            if (this.selectedItems.length >= this.selectedItemsLimit) {
                return;
            }
            this.selectedItems.push(this.leftData.find((x) => x.id === id));
        },
        removeSelectedItems(index) {
            this.selectedItems.splice(index, 1);
        },
        setShownItem(id) {
            this.showItem.id = id;
            this.showItem.name = this.rightData.find((x) => x.id === id).name;
        },
    },
};
</script>

<style scoped>
.main {
    width: calc(100vw - 10px);
    height: 90vh;
    padding: 5px;
}

/* TOP PANEL */

.top-panel {
    margin: 0 auto 20px auto;

    width: 100%;
    height: 200px;

    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.draw-box {
    border: 2px solid black;
}

.item-show {
    width: 30%;

    display: flex;
    justify-content: center;
    align-items: center;
}

.items-group-wrap {
    width: 30%;
    position: relative;
}

.items-group {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: start;

    padding: 10px;
    height: 100%;
    box-sizing: border-box;
}

.item {
    width: 50px;
    height: 50px;
    margin: 5px;
}

.items-group-text {
    position: absolute;
    bottom: 5px;

    width: 100%;
    text-align: center;
}

/* BOT PANEL */
.bot-panel {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
}

.left-column,
.right-column {
    width: 49%;
    height: 60vh;

    display: flex;
    flex-direction: row;
    align-content: flex-start;
    flex-wrap: wrap;
}
</style>
