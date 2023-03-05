<template>
    <div class="main">
        <div class="top-panel">
            <div class="items-group-wrap">
                <div class="items-group draw-box">
                    <div class="item-selected draw-box item">item</div>
                    <div class="item-selected draw-box item">item</div>
                    <div class="item-selected draw-box item">item</div>
                    <div class="item-selected draw-box item">item</div>
                    <div class="item-selected draw-box item">item</div>
                    <div class="item-selected draw-box item">item</div>
                </div>
                <div class="items-group-text">selected: n / m</div>
            </div>
            <div class="item-show draw-box">item-show</div>
        </div>
        <div class="bot-panel">
            <div class="left-column draw-box">
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
            </div>
            <div class="right-column draw-box">
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
                <div class="item-selected draw-box item">item</div>
            </div>
        </div>
    </div>
</template>

<script setup></script>

<style>
body,
* {
    margin: 0;
    padding: 0;
}
</style>

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
}

.items-group-wrap {
    width: 30%;
    position: relative;
}

.items-group {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;

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
    flex-wrap: wrap;
    
}
</style>
