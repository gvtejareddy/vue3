<script setup>
import q from "./data/quizes.json";
import { ref,watch } from "vue";
import Card from "./components/Card.vue"
import { RouterView } from "vue-router";
const quizes= ref(q);
const search = ref("");

watch(search,()=>{
  quizes.value=q.filter(quiz=> quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})


</script>

<template>
  <RouterView/>
  <div class="container">
    <header>
      <h1>Quizes</h1>
      <input v-model.trim="search"  type="text" placeholder="Search...">
    </header>
    <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
  </div>
</template>


<style scoped>
.container {
  max-width: 1000px;
  margin: 0 auto
}

header {
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  align-items: center;
}

header h1 {
  font-weight: bold;
  margin-right: 30px;
}

header input {
  border: none;
  background-color: rgba(128, 128, 128, 0.1);
  padding: 10px;
  border-radius: 5px;
}

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