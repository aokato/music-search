<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          検索結果
        </h1>
        <p>検索キーワード:{{ $route.params.keyword }}</p>
      </v-col>
      <v-col class="mb5" cols="12">
        <div style="margin-bottom:10px" v-for="(album, i) in albums" :key="i">
          <v-card
            color="black"
            dark
            :href="album.collectionViewUrl"
            target="_blank"
          >
            <v-list-item three-line>
              <v-list-item-content class="align-self-start">
                <v-list-item-title
                  class="headline"
                  v-text="album.collectionName"
                ></v-list-item-title>

                <v-list-item-subtitle
                  v-text="album.artistName"
                ></v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-avatar size="125" tile>
                <v-img :src="album.artworkUrl100"></v-img>
              </v-list-item-avatar>
            </v-list-item>
          </v-card>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      albums: []
    };
  },
  created() {
    const vm = this;
    axios
      .get(
        `https://itunes.apple.com/search?term=${this.$route.params.keyword}&entity=album`
      )
      .then(response => {
        console.log(response);
        vm.albums = response.data.results;
      });
  }
};
</script>
