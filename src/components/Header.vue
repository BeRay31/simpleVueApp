<template>
    <div class="container borderNshadow">
        <div class="header-boxs">
            <i class="fas fa-book-reader fa-2x icon" />
            <div class="logo-text use-staat">
                <span>Try Out Online</span>
            </div>
        </div>
        <div class="header-boxs use-staat" v-if="name!=''">
            <span>{{ name }}</span>
        </div>
    </div>
</template>

<script>

    export default {
        props : ['name']
        //data goes here
    }
</script>

<style scoped>
    
    .container {
        border: 4px solid var(--border-color);
        border-width: 0px;
        border-bottom-width: 4px;
        background-color: var(--primary-color);
        display: flex;
        margin: auto;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
    .header-boxs {
        display: flex;
        align-items: center;
        color: var(--background-main-color);
        height: 8vh;
        padding: 1.4em;
        font-size: 1.4vw;
        background-color: var(--secondary-color);
        border-radius: 1em;
        border: 4px solid var(--border-color);
        letter-spacing: 0.07em;
    }

    .logo-text{
        padding-left: 1em;
        letter-spacing: 0.04em;
        text-align: center;
    }

</style>