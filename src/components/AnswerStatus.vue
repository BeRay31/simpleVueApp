<template>
    <div class="ans-status-container">
        <div class="header-status-ans">
            <span>Question Answered</span>
            <span>{{calculcateAns}} of {{ansData.length}}</span>
        </div>
        <div class="status-ans">
            
        </div>
    </div>
</template>

<script>
    export default {
        props:["ansData"],
        data() {
            return {
                qAnswered :0,
            }
        },
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
        }
    }
</script>

<style>
    .ans-status-container {
        background-color: aquamarine;
        margin:0.8em;
    }
    .header-status-ans {
        display: grid;
    }
</style>