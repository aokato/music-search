<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          音楽検索でええええす！！！！！いええええええええええええい！！！！！！！！！！！！
        </h1>
        <v-text-field
          v-model="keyword"
          :counter="100"
          label="アーティスト名を入力してね♡"
          required
        ></v-text-field>
        <v-btn @click="search">SEARCH❕</v-btn>
        <div class="TextAnime1">
          <span
            v-for="(t, index) in text"
            :key="index"
            class="item"
            :style="{ animationDelay: index * 100 + 'ms' }"
            v-text="t"
          />
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      keyword: "",
      text: [
        "このサイトは音楽をアーティスト名で検索するアプリケーションです。",
        "検索にヒットしたアルバムをクリックするとitunesにとびます。"
      ]
    };
  },
  methods: {
    search() {
      this.$router.push(`/result/${this.keyword}`);
    }
  }
};
</script>

<style scoped>
@keyframes text-in {
  0% {
    transform: translate(0, -20px);
    opacity: 0;
  }
}
.item {
  display: inline-block;
  margin-top: 100px;
  min-width: 600px;
  font-size: 2rem;
  animation: text-in 3s cubic-bezier(0.22, 0.15, 0.25, 1.43) 0s backwards;
}
</style>
