<template>
    <div class="q-footer-container">
        <div class="eraseButton" @click="ansData.ans = ''">
            <span>Erase Answer</span>
        </div>
        <div class="controller">
            <span class="logo-arrow" @click="dec()">
                <i class="fas fa-arrow-circle-left fa-2x"/>
            </span>
            <div class="text-box">
                <span>{{ index + 1 }}</span>
            </div>
            <span class="logo-arrow" @click="inc()">
                <i class="fas fa-arrow-circle-right fa-2x"/>
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        props : ["ansData", "index", "inc" , "dec"]
    }
</script>

<style>
    .q-footer-container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        margin: 1em;
    }
    .eraseButton {
        padding: 0.8em;
        border-radius: 0.7em;
        background-color: #edf5e1;
        cursor: pointer;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .eraseButton:hover {
        background-color: #aab19f;
    }
</style>