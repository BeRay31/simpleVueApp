<template>
  <div class="status-container">
      <app-time-status/>
      <app-ans-status :ansData="data" :idx="index"/>
      <div class="submitButton reviewButton touchableButton">
          Submit
      </div>
    </div>
</template>

<script>
    import TimeStatus from './TimeStatus.vue';
    import AnsStatus from './AnswerStatus.vue';

    export default {
        props:["data","index"],
        components: {
            appTimeStatus : TimeStatus,
            appAnsStatus : AnsStatus,
        }
    }
</script>

<style>
    .status-container{
        margin: 0 1em;
        border-radius: 3vh;
        display: grid;
        grid-template-rows: 35% 55% 10%;
        align-items: center;
        justify-items: center;
    }
    .submitButton {
        margin: auto;

    }

</style>