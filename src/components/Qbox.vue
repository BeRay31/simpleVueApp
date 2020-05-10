<template>
    <div class="q-box-container">
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
        background-color: #edf5e1;
        border-radius: 0.8em;
        margin: 1em;
        padding: 1em;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
</style>