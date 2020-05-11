<template>
  <div class="time-status-container borderNshadow use-staat">
    <div class="header-text ">
      <span class="borderNshadow">Sisa Waktu Sesi</span>
    </div>
    <div class="box-time">
        <div class="box-status borderNshadow">
          <span class="box-status-time">{{Math.floor(time/3600)}}</span>
          <span class="box-details">Jam</span>
        </div>
        <div class="box-status borderNshadow">
          <span class="box-status-time">{{Math.floor((time%3600)/60)}}</span>
          <span class="box-details">menit</span>
        </div>
          <div class="box-status borderNshadow">
          <span class="box-status-time">{{(time%3600)%60}}</span>
          <span class="box-details">detik</span>
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
        background-color: var(--secondary-color);
        margin: 1em;
        padding: 1em;
        border-radius: 1.4em;
        width: 90%;
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
    .header-text > span {
      letter-spacing: 0.04em;
      font-size: 1.7vw;
      color: var(--background-main-color);
      background-color: var(--background-main-color);
      color: black;
      padding: 0.4em;
      border-radius: 1vw;
    }
    .box-time {
      display: grid;
      align-items: center;
      justify-items: center;
      grid-template-columns: 1fr 1fr 1fr;
    }
    .box-status {
      display :grid;
      justify-items: center;
      align-items: center;
      margin : 0.3em;
      margin: 1.4em;
      height: 60%;
      width: 80%;
      border-radius: 20%;
      background-color: var(--background-main-color);
      cursor: default;
    }
    .box-status-time {
      font-size: 2vw;
      margin-top: 0.5em;
    }
    .box-details {
      margin-bottom: 0.3em;
      font-size: 1.2vw;
    }
</style>