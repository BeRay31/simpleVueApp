<template>
  <div class="status-container">
      <app-time-status/>
      <app-ans-status :ansData="data" :idx="index"/>
      <div class="submitButton reviewButton touchableButton borderNshadow use-staat">
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
        height: 60%;
        width: 100%;
        align-items: center;
        justify-items: center;
    }
    .submitButton {
        background-color: var(--secondary-color);
        color: var(--background-main-color);
        margin: auto;
        letter-spacing: 0.08em;
        font-size: 1.2vw;
    }
    .submitButton:hover {
        background-color: var(--primary-color);
        border-color: var(--secondary-border-color);
        color: black;
    }

</style>