<template>
  <div class="container">
    <b-input size="lg" type="text" v-model="keyword" />
    <b-button size="" text="Button" variant="success" @click="searchData()"
      >Search for Gifs</b-button
    >
    <p><br /></p>

    <iframe
      width="420"
      height="315"
      src="https://www.youtube.com/embed/gdZLi9oWNZg"
      frameborder="0"
      allowfullscreen
    ></iframe>
    <p><br /></p>
    <div>
      <b-card-group columns>
        <b-card
          v-for="data in resultData"
          :key="data.id"
          style="max-width: 30rem"
          :header="data.title"
          header-bg-variant="dark"
          header-text-variant="white"
          align="center"
          class="mb-2"
        >
          <b-embed
            class="rounded"
            type="video"
            :key="data.id"
            :src="data.images.original.mp4"
            autoplay=""
            loop=""
            style="max-width: 100%"
          ></b-embed>

          <b-card-text>{{ data.import_datetime }}</b-card-text>
          <b-button :href="data.url" variant="dark">Go somewhere</b-button>
        </b-card>
      </b-card-group>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      resultData: null,
      keyword: "",
    };
  },
  methods: {
    searchData() {
      axios
        .get(
          "https://api.giphy.com/v1/gifs/search?api_key=39vI8skUqOzHnLMOJZiRkLKJ7SIWbQ4J&q=" +
            this.keyword +
            "&limit=30&rating=g"
        )
        .then((response) => {
          this.resultData = response.data.data;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

<style>
</style>

