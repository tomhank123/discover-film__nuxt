<template>
  <section>
    <v-card flat tile class="cyan darken-3 py-8">
      <v-container>
        <v-card-text class="pa-0">
          <p class="text-h2 text--primary">Welcome.</p>
          <p class="ma-0 text-uppercase">
            Millions of movies, TV shows and Card.Texteople to discover. Explore
            now.
          </p>
        </v-card-text>
      </v-container>
    </v-card>
    <v-container>
      <v-row v-if="loading" class="my-10">
        <v-col v-for="card in 4" :key="card" cols="3" md="4" lg="3">
          <celeb-card v-bind="{ loading: loading }" />
        </v-col>
      </v-row>
      <v-row v-else class="my-10">
        <v-col v-for="card in cards" :key="card.title" cols="3" md="4" lg="3">
          <celeb-card v-bind="{ celeb: card }" />
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  data: () => ({
    loading: false,
    cards: false,
  }),
  mounted() {
    this.loading = true

    setTimeout(() => {
      this.loading = false
      this.cards = [
        {
          id: 1,
          title: 'Pre-fab homes',
          src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
        },
        {
          id: 2,
          title: 'Favorite road trips 1',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
        },
        {
          id: 3,
          title: 'Best airlines 2',
          src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
        },
        {
          id: 1,
          title: 'Pre-fab homes 3',
          src: 'https://cdn.vuetifyjs.com/images/cards/cooking.png',
        },
        {
          id: 4,
          title: 'Favorite road trips 4',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
        },
        {
          id: 5,
          title: 'Best airlines 5',
          src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
        },
      ]
    }, 3000)
  },
}
</script>
