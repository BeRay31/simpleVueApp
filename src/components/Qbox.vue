<template>
    <div class="q-box-container borderNshadow use-sans-pro">
        <p>{{ question }}</p>
    </div>
</template>

<script>
export default {
    props:["question"],
}
</script>

<style>
    .q-box-container {
        background-color: var(--background-main-color);
        font-size: 1.2vw;
        border-radius: 0.8em;
        margin: 1em;
        padding: 1em;
    }
</style>