<template>
    <div class="container">
        <div class="logo">
            <i class="fas fa-book-reader fa-2x" />
            <div class="logo-text">
                <p>Simple</p>
                <p>TryOut</p>
                <p>Apps</p>
            </div>
        </div>
        <div class="navbar">
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
        width: 100%;
        height: 100%;
        background-color: #a8d0e6;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
        display: flex;
        margin: auto;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }
    .logo {
        padding : 1em;
        color: "#edf5e1";
        display: flex;
        align-content: center;
        justify-content: center;
    }

    .logo-text{
        padding-left: 1em;
        text-align: center;
    }

    .navbar {
        padding : 1em;
    }

</style>