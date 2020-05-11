<template>
    <div class="container-question borderNshadow">
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
    import { eventBus } from '../main.js'

    export default {
        props:["data","index"],
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
                    this.$emit('indexChanged',this.index);
                }
            },
            indexDec () {
                if(this.index>0) {
                    this.index--;
                    this.$emit('indexChanged',this.index);
                }
            }
        },
        created() {
            eventBus.$on('indexEdited',(data)=>{
                this.index = data;
                this.$emit('indexChanged',this.index);
             });
        },
    }
</script>

<style scoped>
    .container-question {
        background-color: var(--secondary-color);
        margin: 0 0.5em;
        border-radius: 3vh;
        display : grid;
    }
</style>