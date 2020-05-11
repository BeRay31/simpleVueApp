<template>
  <div class="q-ans-container borderNshadow use-sans-pro">
      <div class="instruction">
          <span>{{ ansData.instruction }}</span>
      </div>
      <div class="ans">
        <input type="radio" value="A" v-model="ansData.ans">
        <label for="A" @click='ansData.ans = "A"'>A</label>
        <span>{{ ansData.ansA }}</span>
      </div>
      <div class="ans">
        <input type="radio" value="B" v-model="ansData.ans">
        <label for="B" @click='ansData.ans = "B"'>B</label>
        <span>{{ ansData.ansB }}</span>
      </div>
      <div class="ans">
        <input type="radio" value="C" v-model="ansData.ans">
        <label for="C" @click='ansData.ans = "C"'>C</label>
        <span>{{ ansData.ansC }}</span>
      </div>
      <div class="ans">
        <input type="radio" value="D" v-model="ansData.ans">
        <label for="D" @click='ansData.ans = "D"'>D</label>
        <span>{{ ansData.ansD }}</span>
      </div>
      <div class="ans">
        <input type="radio" value="E" v-model="ansData.ans">
        <label for="E" @click='ansData.ans = "E"'>E</label>
        <span>{{ ansData.ansE }}</span>
      </div>
  </div>
</template>

<script>
  export default {
    props: ["ansData"],
  }
</script>

<style>
    .q-ans-container {
        background-color: var(--background-main-color);
        margin: 1em;
        padding: 1em;
        font-size: 1.2vw;
        border-radius: 1em;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .instruction {
      margin-bottom: 0.8em;
    }
    .ans {
      margin: 2em;
      display: flex;
      align-items: center;
      justify-items: center;
    }
    .ans > span {
      margin-left: 1em;
    }
    .ans > input {
      display: none;
    }
    .ans > label {
      cursor:pointer;
      background-color: var(--background-main-color);
      height: 2em;
      width: 2em;
      padding: 1em;
      border-radius: 1.2em;
      display: inline-flex;
      align-items: center;
      justify-content: center;   
      text-align: center;
      transition:all .5s ease;
      border: 2px solid var(--secondary-color);
    }
    .ans > label:hover {
      background-color: var(--hover-color);
      transition:all .5s ease;
    }

    .ans > input:checked + label {
      transition:all .5s ease;
      background:var(--secondary-color);
      color:#fff;
    }
</style>