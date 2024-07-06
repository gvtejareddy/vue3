<script setup>
import { defineProps } from 'vue';

const {quiz}=defineProps(['quiz'])

console.log(quiz)

</script>

<template>
        <div  class="gallery" >
      <a target="_blank" href="">
        <img :src="quiz.img" width="600" height="400">
      </a>
      <div class="card-text">
            <h2>{{ quiz.name }}</h2>
            <p>{{ quiz.questions.length }} questions</p>
        </div>
    </div>

</template>
<style scoped>
div.gallery {
  margin: 5px;
  border: 1px solid #ccc;
  float: left;
  width: 180px;
}

div.gallery:hover {
  border: 1px solid #777;
}

div.gallery img {
  width: 100%;
  height: auto;
}

div.desc {
  padding: 15px;
  text-align: center;
}
.card-text {
    padding: 0 5px
  }

  .card-text h2 {
    font-weight: bold;
  }
</style>
