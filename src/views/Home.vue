<template>
  <div class="home">
    <div class="container">
      <h4 :class="{ subheading: true, dark: darkmode }">This Season</h4>
      <div class="card-container">
        <div v-for="anime in animeCollection" :key="anime.id" class="card">
          <img :src="require('../assets/img/' + anime.url)" alt="anime.title" />
          <div class="card-title">
            <span>
              {{ anime.title }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
  import animeCollection from '../animeCollection';

  export default {
    props: ['darkmode'],
    created() {
      document.title = "Ryuuganime - Home";
    },
    data() {
      return {
        animeCollection: animeCollection
      }
    }
  }
</script>