<template>
    <div class="q-header-container">
        <div class="topic">
            <span><u class="use-sans-pro">{{ topic }}</u></span>
        </div>
        <div class="controller">
            <i class="fas fa-arrow-circle-left fa-2x logo-arrow" @click="dec()"/>
            <div class="text-box use-staat">
                <span>{{ index + 1 }}</span>
            </div>
            <i class="fas fa-arrow-circle-right fa-2x logo-arrow" @click="inc()"/>
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
        color: var(--background-main-color);
        margin: 1em;
    }
    .topic {
        padding: 0.3em;
        font-size: 1.6vw;
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
        width: 2.6vw;
        height: 2.6vw;
        border-radius: 1.3em;
        display: flex;
        align-items: center;
        justify-content: center;   
        text-align: center;
        margin: auto;
        cursor: default;
        letter-spacing: 0.08em;
        border: 4px solid var(--border-color);
    }
    .logo-arrow {
        display: grid;
        align-items: center;
        justify-items: center;
        width: 2.6vw;
        height: 2.6vw;
        border-radius: 1.3em;
        color: var(--background-main-color);
        cursor: pointer;
    }
    .logo-arrow:hover {
        color: var(--hover-color);
        transition:all .5s ease;
    }
</style>