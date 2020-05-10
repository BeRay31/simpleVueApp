<template>
    <div class="q-header-container">
        <div class="topic">
            <span>{{ topic }}</span>
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
    props :[ "topic", "index", "inc", "dec" ]
}
</script>

<style>
    .q-header-container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        margin: 1em;
    }
    .topic {
        padding: 0.3em;
        font-size: 1.6em;
    }
    .controller {
        width: 20%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
        padding: 0.3em;
    }
    .text-box {
        background-color:var(--background-main-color);
        color: black;
        width: 2em;
        height: 2em;
        border-radius: 1em;
        display: flex;
        align-items: center;
        justify-content: center;   
        text-align: center;
        margin: auto;
        cursor: default;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);

    }
    .logo-arrow {
        width: 2em;
        height: 2em;
        border-radius: 1em;
        color: #edf5e1;
        cursor: pointer;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .logo-arrow:hover {
        color: #aab19f;
    }
</style>