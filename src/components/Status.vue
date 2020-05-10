<template>
  <div class="status-container">
      <app-time-status/>
      <app-ans-status/>
      <div class="button-finish">

      </div>
  </div>
</template>

<script>
    import TimeStatus from './TimeStatus.vue';
    import AnsStatus from './AnswerStatus.vue';

    export default {
        components: {
            appTimeStatus : TimeStatus,
            appAnsStatus : AnsStatus,
        }
    }
</script>

<style>
    .status-container{
        background-color: #a8d0e6;
        margin: 0 1em;
        border-radius: 3vh;
        height: 60%;
        display: grid;
        grid-template-rows: 3fr 5fr 1fr;
    }
    .button-finish {
        background-color: yellow;
        margin: 0.3em 1em;
    }
</style>