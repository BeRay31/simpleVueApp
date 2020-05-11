<template>
  <div class="status-container">
      <app-time-status :timesUp="timeUp"/>
      <app-ans-status :ansData="data" :idx="index"/>
      <div class="submitButton reviewButton touchableButton borderNshadow use-staat" @click="submitted()">
          Kumpulkan Jawaban
      </div>
    </div>
</template>

<script>
    import TimeStatus from './TimeStatus.vue';
    import AnsStatus from './AnswerStatus.vue';

    export default {
        props:["data","index","changeStatus"],
        components: {
            appTimeStatus : TimeStatus,
            appAnsStatus : AnsStatus,
        },
        methods :{
            submitted() {
                let val = confirm("Apakah anda yakin?");
                if(val) {
                    this.$emit('submitted')
                }
            },
            timeUp(){
                this.$emit('submitted');
            }
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
        width: 60%;
        text-align: center;
        padding: 0.6em;
        letter-spacing: 0.12em;
        font-size: 1.2vw;
    }
    .submitButton:hover {
        background-color: var(--primary-color);
        border-color: var(--secondary-border-color);
        color: black;
    }

</style>