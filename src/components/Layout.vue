<template>
     <main class="cards">
          <Card v-for="card in cards" :key="card.id" :data="card" />
     </main>
</template>

<script setup lang="ts">
import Card from "./Card.vue";

const cards = [
     {
          id: 0,
          title: "YOUR SPRING LOOK",
          subtitle: "Daytime dressing pure&simple",
          link: "http://google.com",
          reverse: false,
          photoName: "photoOne",
     },
     {
          id: 1,
          title: "MODERN BUSINESS OUTFIT",
          subtitle: "Smart casual for you",
          link: "http://google.com",
          reverse: true,
          photoName: "photoOne",
     },
     {
          id: 2,
          title: "NEW STREET STYLE",
          subtitle: "Discover the art of outdor",
          link: "http://google.com",
          reverse: false,
          photoName: "photoOne",
     },
];
</script>

<style scoped lang="scss">

@import '../assets/styles/style.scss';
.cards {
     width: 90%;
     margin-top: 50px;
     @extend %flex--horizontal;
}
</style>
