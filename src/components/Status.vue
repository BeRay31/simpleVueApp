<template>
  <div class="status-container">
      <app-time-status/>
      <app-ans-status :ansData="data"/>
      <div class="button-finish">

      </div>
  </div>
</template>

<script>
    import TimeStatus from './TimeStatus.vue';
    import AnsStatus from './AnswerStatus.vue';

    export default {
        props:["data"],
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
        display: grid;
        grid-template-rows: 35% 55% 10%;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .button-finish {
        background-color: yellow;
        margin: 0.8em;
    }
</style>