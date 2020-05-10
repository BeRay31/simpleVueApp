<template>
    <div class="container-question">
        <app-question-header/>
        <app-question-box/>
        <app-question-ans/>
        <app-question-footer/>
    </div>
</template>

<script>
    import appQuestionHeader from './Qheader.vue';
    import appQuestionFooter from './Qfooter.vue';
    import appQuestionBox from './Qbox.vue';
    import appQuestionAns from './Qans.vue';

    export default {
        components : {
            appQuestionHeader,
            appQuestionFooter,
            appQuestionBox,
            appQuestionAns
        }
    }
</script>

<style scoped>
    .container-question {
        background-color: #a8d0e6;
        margin: 0 1em;
        border-radius: 3vh;
        display : grid;
        grid-template-rows: 1fr 3fr 2fr 1fr;
    }
</style>