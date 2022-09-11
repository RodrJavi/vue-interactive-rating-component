<script setup>
import { ref } from "vue";

const score = ref(1);

const submitScore = (e) =>{
  score.value = e.target.elements.score.value;
  document.getElementById("ratingState").style.display = "none";
  document.getElementById("thankState").style.display = "flex";
}

</script>

<template>
  <div id="ratingState">
    <h1>How did we do?</h1>
    <p>Please let us know how we did with your support request. All
      feedback is appreciated to help us improve our offering!</p>
    <form @submit.prevent="submitScore" action="">
      <div>
        <input type="radio" name="score" id="one" value="1">
        <label for="one">1</label>
        <input type="radio" name="score" id="two" value="2">
        <label for="two">2</label>
        <input type="radio" name="score" id="three" value="3">
        <label for="three">3</label>
        <input type="radio" name="score" id="four" value="4">
        <label for="four">4</label>
        <input type="radio" name="score" id="five" value="5">
        <label for="five">5</label>
      </div>
      <button type="submit">SUBMIT SCORE</button>
    </form>
  </div>
  <div id="thankState" :style="{display: 'none'}">
    <span>You selected {{score}} out of 5 </span>
    <h2>Thank you!</h2>
  </div>
</template>