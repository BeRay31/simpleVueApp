<template>
    <div class="ans-status-container borderNshadow use-staat">
        <div class="header-status-ans borderNshadow">
            <span>{{calculcateAns}} dari {{ansData.length}}</span>
            <span>terjawab</span>
        </div>
        <div class="panel-ans">
            <div class="ans-sheet"
            v-for="(data,index) in ansData" 
            :key="index" 
            ><span 
            class="text-box panel-items borderNshadow" 
            :class="{
                answered : ansData[index].ans != '',
                'active-index' : index==idx,
            }" 
            @click="changeQuestion(index)"
            >{{ index+1 }}</span>
            <span class="text-ans" v-if="ansData[index].ans!=''">{{ansData[index].ans}}</span>
            <span class="text-ans" v-else>-</span>
            </div>
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
        },
    }
</script>

<style>
    .ans-status-container {
        letter-spacing: 0.06em;
        background-color: var(--secondary-color);
        margin: 1em;
        padding: 1em;
        border-radius: 1.4em;
        width: 90%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-items: center;
        font-size: 1.2vw;
    }
    .header-status-ans {
        display: grid;
        align-items: center;
        justify-content: center;
        background-color: var(--background-main-color);
        padding: 0.2em;
        width: 50%;
        border-radius: 1em;
    }
    .header-status-ans > span {
        margin : 0.5em;
        text-align: center;
    }
    .panel-ans {
        display: grid;
        justify-items: center;
        grid-template-columns: repeat(5,1fr);
        margin-top: 1em;
    }
    .panel-items {
        width: 2.8vw;
        height: 2.8vw;
        border-radius: 1.4em;
        background-color: var(--background-main-color);
        margin: 0.8em;
        cursor: pointer;
    }
    .panel-items:hover {
        background-color:var(--hover-color);
        color: black;
        transition:all .5s ease;
    }
    .answered {
        background-color: var(--border-color);
        color: var(--background-main-color);
        transition:all .4s ease;
        border-color: var(--primary-color);
    }
    .active-index {
        background-color: var(--secondary-color);
        color: var(--background-main-color);
        border-color: var(--primary-color);
        transition:all .5s ease;
    }
    .ans-sheet{
        display: inline-flex;
        align-items: center;
    }
    .text-ans {
        font-size: 1.2vw;
    }

</style>