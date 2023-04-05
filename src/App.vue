<script setup>
import data from '../data/data.json'
import { ref } from 'vue'

const quizes = ref(data)
</script>

<template>
  <div class="container">
    <header>
      <h1>Quizes</h1>
      <input type="text" placeholder="search..." />
    </header>
    <div class="options__container">
      <div v-for="quiz in quizes" :key="quiz.id" class="card">
        <img :src="quiz.img" alt="">
        <div class="card__body">
          <h2>{{ quiz.name }}</h2>
          <p>{{ quiz.questions.length }} questions</p>
        </div>
      </div>
    </div>
  </div>
</template>



<style scoped lang="scss" >
.container {
  max-width: 1000px;
  margin: 0 auto;
  padding-top: 50px;

  header {
    width: 100%;
    display: flex;
    align-items: center;
    /* justify-content: center; */

    margin-bottom: 50px;

    h1 {
      font-weight: bold;
      margin-right: 20px;
    }

    input {
      border: none;
      background-color: rgba(128, 128, 128, .1);
      padding: 10px;
      border-radius: 5px;
    }

  }

  .options__container {
    display: flex;
    gap: 40px;

    .card {
      width: 300px;
      overflow: hidden;
      border-radius: 2%;
      box-shadow: 1px 1px 10px rgba(0, 0, 0, .1);
      cursor: pointer;

      &>img {
        width: 100%;
        height: 190px;
        margin: 0;
      }

      &__body {
        padding: 0 5px;

        h2 {
          font-weight: bold;
        }
      }
    }
  }
}
</style>
