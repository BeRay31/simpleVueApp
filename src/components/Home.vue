<template>
  <div class="home-container">
      <div class="welcome-text borderNshadow">
          <span class="use-staat">Try Out UTBK !</span>
      </div>
      <div class="input-box use-staat">
        <div class="input-area use-staat borderNshadow">
            <p> <u>Masukkan Namamu !</u></p>
            <input type="text" name="nama" v-model="nama">
        </div>
          <div class="enter-name borderNshadow" @click="changeName">
              Mulai
          </div>
          <p>Klik untuk mulai !</p>
      </div>
  </div>
</template>

<script>
    export default {
        data() {
            return {
                nama : '',
            }
        },
        methods:{
            changeName() {
                if(this.nama!='' && this.nama.length<30) {
                    alert("Anda akan memulai Ujian !");
                    this.$emit('nameChanged',this.nama);
                }
                else if(this.name=='') {
                    alert("Masukkan nama anda!");
                } else {
                    alert("Nama Terlalu panjang (harus kurang dari 30 karakter)")
                }
            }
        }
    }
</script>

<style>
    .home-container {
        height: 60vh;
        width: 60vw;
        margin: auto;
        margin-top: 15vh;
        border-radius: 7vh;
        display: grid;
        justify-items: center;
        cursor: default;
    }
    .welcome-text {
        display: grid;
        align-items: center;
        justify-items: center;
        margin: auto;
        font-size: 2.3vw;
        width: 20vw;
        height: 10vh;
        border-radius: 10vh;
        background-color: var(--secondary-color);
        color: var(--background-main-color);
    }
    .input-box {
        width: 40vw;
        height: 40vh;
        border-radius: 3vh;
        margin: auto;
        display: grid;
        justify-items: center;
        align-items: center;
        font-size: 2vw;
        letter-spacing: 0.06em;
    }
    .input-box > p {
        margin-top: 1em;
        font-size: 0.6em;
    }
    .welcome-text > span {
        letter-spacing: 0.04em;
    }
    .enter-name {
        display: grid;
        align-items: center;
        justify-items: center;
        margin: auto;
        margin-top: 1em;
        width: 12vw;
        height: 8vh;
        border-radius: 10vh;
        background-color: var(--secondary-color);
        color: var(--background-main-color);
    }
    .input-area{
        color: var(--background-main-color);
        width: 24vw;
        height: 30vh;
        border-radius: 4vh;
        display: grid;
        justify-items: center;
        align-items: center;
        background-color: var(--secondary-color);
    }
    .input-area > input {
        text-align: center;
        font-family: inherit;
        letter-spacing: 0.05em;
        font-size: 0.8em;
        width : 80%;
        height: 40%;
        border-radius: 2em;
    }
    .enter-name:hover {
        background-color: var(--hover-color);
        transition:all .5s ease-in;
        color: black;
        cursor: pointer;
    }
    
</style>