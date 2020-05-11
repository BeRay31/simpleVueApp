<template>
    <div class="submit-container use-staat">
       <div class="res-container">
            <div class="welcome-text borderNshadow">
                <span class="use-staat">Hasil Ujian</span>
            </div>
            <div class="panel-ans panel-res">
                <div class="ans-sheet "
                v-for="(d,index) in data" 
                :key="index" 
                >
                    <span 
                    class="text-box panel-items borderNshadow"
                    :class="{
                        'wrong-ans': data[index].ans != questionKey[index],
                        'right-ans': data[index].ans == questionKey[index],
                        }" 
                    >{{ index+1 }}</span>
                    <span class="text-ans" v-if="data[index].ans!=''">{{data[index].ans}}</span>
                    <span class="text-ans" v-else>-</span>
                </div>
            </div>
            <div class="welcome-text borderNshadow value-container">
                <span class="use-staat"> Nilai Mu : {{calculateExam()}}</span>
            </div>
       </div>
    </div>
</template>

<script>
export default {
    props: ["questionKey","data"],
    methods :{
        calculateExam() {
            let val = 0
            for(let i = 0; i<this.data.length;i++) {
                if(this.data[i].ans == this.questionKey[i]) {
                    val++;
                }
            }
            return (val/this.data.length)*100
        },
        calculateRightAns(){
            let val = 0
            for(let i = 0; i<this.data.length;i++) {
                if(this.data[i].ans == this.questionKey[i]) {
                    val++;
                }
            }
            return val;            
        }
    }
}
</script>

<style>
    .submit-container {
        height: 80vh;
        width: 40vw;
        margin: auto;
        margin-top: 5vh;
        border-radius: 7vh;
        justify-items: center;
        cursor: default;
        border-color: var(--secondary-color);
        align-items: center;
    }
    .wrong-ans {
        background-color: #fb3862;
        color: var(--background-main-color);
    }
    .right-ans {
        background-color: rgb(0, 255, 136);
    }
    .value-container {
        width: 20vw;
    }
    .panel-res {
        padding: 1em;
    }
    .detail-res {
        height: 50%;
        width: 30vw;
        background-color: var(--background-main-color);
        border-radius: 1.8vw;
        padding: 1em;
    }
</style>