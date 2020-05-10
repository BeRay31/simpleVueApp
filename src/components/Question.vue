<template>
    <div class="container-question">
        <app-question-header :topic="data[index].topic" :index="index" :inc="indexInc" :dec="indexDec"/>
        <app-question-box :question="data[index].question"/>
        <app-question-ans :ansData="data[index]"/>
        <app-question-footer  :ansData="data[index]" :index="index" :inc="indexInc" :dec="indexDec"/>
    </div>
</template>

<script>
    import appQuestionHeader from './Qheader.vue';
    import appQuestionFooter from './Qfooter.vue';
    import appQuestionBox from './Qbox.vue';
    import appQuestionAns from './Qans.vue';

    export default {
        props:["data"],
        data() {
            return {
                index : 0,
            }
        },
        components : {
            appQuestionHeader,
            appQuestionFooter,
            appQuestionBox,
            appQuestionAns
        },
        methods : {
            indexInc () {
                if(this.index<this.data.length-1) {
                    this.index++;
                }
            },
            indexDec () {
                if(this.index>0) {
                    this.index--;
                }
            }
        }
    }
</script>

<style scoped>
    .container-question {
        background-color: #a8d0e6;
        margin: 0 0.5em;
        border-radius: 3vh;
        display : grid;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
</style>