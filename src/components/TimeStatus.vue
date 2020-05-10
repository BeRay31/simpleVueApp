<template>
  <div class="time-status-container">
    <div class="header-text">
      <span>Sisa Waktu Sesi</span>
    </div>
    <div class="box-time">
        <div class="box-status">
          <span class="box-status-time">{{Math.floor(time/3600)}}</span>
          <span class="box-details">hours</span>
        </div>
        <div class="box-status">
          <span class="box-status-time">{{Math.floor((time%3600)/60)}}</span>
          <span class="box-details">minute</span>
        </div>
    </div>
    <div class="detail-time">
      <span>Sisa Waktu Try Out : {{Math.floor(time/3600)}}:{{Math.floor((time%3600)/60)}}:{{(time%3600)%60}} </span>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        time : 7200, 
      }
    },
    created() {
      let timer = setInterval(()=>{
        if(this.time>0) {
          this.time--;
        } else {
          clearInterval(timer);
          alert("Your Time is Up");
          //submit button triggered
        }
      },1000)
    }
  }
</script>

<style>
    .time-status-container{
        margin: 0.8em;
        display: grid;
        justify-content: center;
        grid-template-rows: 1fr 2fr 1fr;
    }
    .header-text {
      display: flex;
      justify-content: center;
      align-items: center;
      margin : 0.3em;
    }
    .box-time {
      display: grid;
      align-items: center;
      justify-items: center;
      grid-template-columns: 1fr 1fr;
    }
    .box-status {
      background-color: aqua;
      display :flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin : 0.3em;
      margin: 2em;
      height: 60%;
      width: 80%;
      border-radius: 20%;
      background-color: #edf5e1;
      box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .box-status-time {
      font-size: 30px;
      margin-bottom: 0.5em;
    }
    .box-details {
      font-size: 18px;
    }
    .detail-time {
      display: flex;
      justify-content: center;
      align-items: center;
    }
</style>