<template>
  <div class="q-ans-container">
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
      <p>{{ansData.ans}}</p>
  </div>
</template>

<script>
  export default {
    props: ["ansData"],
  }
</script>

<style>
    .q-ans-container {
        background-color: #edf5e1;
        margin: 1em;
        padding: 1em;
    }
    .instruction {
      background-color: aqua;
      margin-bottom: 0.8em;
    }
    .ans {
      margin: 2em;
    }
    .ans > span {
      margin-left: 1em;
    }
    .ans > input {
      display: none;
    }
    .ans > label {
      cursor:pointer;
      background-color: #edf5e1;
      color: black;
      width: 1.8em;
      height: 1.8em;
      border-radius: 0.9em;
      display: inline-flex;
      align-items: center;
      justify-content: center;   
      text-align: center;
      box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
      transition:all .7s ease;
    }
    .ans > label:hover {
      background-color: #aab19f;
    }

    .ans > input:checked + label {
      background:#009ACE;
      color:#fff;
    }
</style>