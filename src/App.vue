<template>
  <v-app>
    <v-app-bar app color="pink" dark>
      <v-toolbar-title class="headline text-uppercase">
        <router-link to="/" style="color:white;text-decoration:none;">
          <span>Ongaku Search</span>
        </router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <p>by yasunari</p>
      <v-btn to="/" text>
        <span class="mr-2">HOUSE</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-content class="v-content">
      <router-view />
    </v-content>
  </v-app>
</template>

<script>
export default {};
</script>
<style>
.v-content {
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
}
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>
