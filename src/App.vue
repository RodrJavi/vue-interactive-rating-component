<script setup>
import { ref } from "vue";

const score = ref(1);
const complete = ref(false);

const submitScore = (e) =>{
  complete.value = true;
}

</script>

<template>
  <div v-if="!complete">
    <h1>How did we do?</h1>
    <p>Please let us know how we did with your support request. All
      feedback is appreciated to help us improve our offering!</p>
    <form @submit.prevent="submitScore">
      <div>
        <input type="radio" name="score" id="one" value="1" v-model="score">
        <label for="one">1</label>
        <input type="radio" name="score" id="two" value="2" v-model="score">
        <label for="two">2</label>
        <input type="radio" name="score" id="three" value="3" v-model="score">
        <label for="three">3</label>
        <input type="radio" name="score" id="four" value="4" v-model="score">
        <label for="four">4</label>
        <input type="radio" name="score" id="five" value="5" v-model="score">
        <label for="five">5</label>
      </div>
      <button type="submit">SUBMIT SCORE</button>
    </form>
  </div>
  <div v-else>
    <span>You selected {{score}} out of 5 </span>
    <h2>Thank you!</h2>
  </div>
</template>