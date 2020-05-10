<template>
  <div class="time-status-container">
    <div class="header-text">
      <span>Sisa Waktu Sesi</span>
    </div>
    <div class="box-time">
        <div class="box-status">
          <span class="box-status-time">{{Math.floor(time/3600)}}</span>
          <span class="box-details">Hours</span>
        </div>
        <div class="box-status">
          <span class="box-status-time">{{Math.floor((time%3600)/60)}}</span>
          <span class="box-details">Minute</span>
        </div>
          <div class="box-status">
          <span class="box-status-time">{{(time%3600)%60}}</span>
          <span class="box-details">Second</span>
        </div>
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
        background-color: var(--primary-color);
        margin: 1em;
        padding: 1em;
        border-radius: 1.4em;
        width: 90%;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
        margin: 0.8em;
        display: grid;
        justify-content: center;
        grid-template-rows: 1fr 2fr;
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
      grid-template-columns: 1fr 1fr 1fr;
    }
    .box-status {
      display :flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin : 0.3em;
      margin: 1.4em;
      height: 60%;
      width: 80%;
      border-radius: 20%;
      background-color: #edf5e1;
      box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
      border: 3px solid var(--secondary-color);
    }
    .box-status-time {
      font-size: 30px;
      margin-top: 0.5em;
    }
    .box-details {
      margin-bottom: 0.3em;
      font-size: 18px;
    }
</style>