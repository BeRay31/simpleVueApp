<template>
    <div class="ans-status-container">
        <div class="header-status-ans">
            <span>Question Answered</span>
            <span>{{calculcateAns}} of {{ansData.length}}</span>
        </div>
        <div class="panel-ans">
            <div class="text-box panel-items" 
            :class="{
                answered : ansData[index].ans != '',
                'active-index' : index==idx,
            }" 
            v-for="(data,index) in ansData" 
            :key="index" 
            @click="changeQuestion(index)"
            ><span>{{ index+1 }}</span>
            </div>
        </div>
        <div class="touchableButton reviewButton">
            Review
        </div>
    </div>
</template>

<script>
    import {eventBus} from './../main'
    export default {
        props:["ansData","idx"],
        computed :{
            calculcateAns() {
                let ans = 0;
                for(let i = 0; i<this.ansData.length;i++) {
                    if(this.ansData[i].ans != '') {
                        ans++;
                    }
                }
                return ans;
            }
        },
        methods :{
            changeQuestion(index) {
                eventBus.changeIndex(index);
            }
        }
    }
</script>

<style>
    .ans-status-container {
        background-color: var(--primary-color);
        margin: 1em;
        padding: 1em;
        border-radius: 1.4em;
        width: 90%;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .header-status-ans {
        display: grid;
        align-items: center;
        justify-content: center;
    }
    .header-status-ans > span {
        margin : 0.5em;
        text-align: center;
    }
    .panel-ans {
        display: grid;
        grid-template-columns: repeat(5,1fr);
        margin-top: 1em;
    }
    .panel-items {
        width: 2.3em;
        height: 2.3em;
        border-radius: 1.4em;
        background-color: var(--background-main-color);
        margin: 0.6em;
        cursor: pointer;
        border: 3px solid var(--secondary-color);
    }
    .panel-items:hover {
        background-color:var(--hover-color);
        color: var(--background-main-color);
    }
    .answered {
        background-color: var(--secondary-color);
        transition:all .4s ease;
        color: var(--background-main-color);
    }
    .active-index {
        background-color: var(--active-link-color);
        color: var(--background-main-color);
    }
    .reviewButton{
        text-align: center;
        margin: 0.3em;
        margin-top: 2em;
        width: 40%;
    }
</style>