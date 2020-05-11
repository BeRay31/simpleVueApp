<template>
    <div class="q-footer-container use-staat">
        <div class="touchableButton borderNshadow" @click="ansData.ans = ''">
            <span>Hapus jawaban</span>
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
        letter-spacing: 0.08em;
    }
    .touchableButton {
        padding: 0.8em;
        font-size: 1.1vw;
        border-radius: 0.7em;
        cursor: pointer;
        background-color: var(--background-main-color);
    }
    .touchableButton:hover {
        background-color: var(--border-color);
        transition:all .5s ease;
        border-color: var(--primary-color);
        color: var(--background-main-color);
    }
</style>