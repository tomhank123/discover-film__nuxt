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
        <v-col v-for="card in 6" :key="card" cols="2">
          <media-card v-bind="{ loading: loading }" />
        </v-col>
      </v-row>
      <v-row v-else class="my-10">
        <v-col v-for="card in cards" :key="card.title" cols="2">
          <media-card v-bind="{ media: card }" />
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
    this.loading = true;

    setTimeout(() => {
      this.loading = false;
      this.cards = [
        {
          title: 'Pre-fab homes',
          src: 'https://www.themoviedb.org/t/p/w440_and_h660_face/kEl2t3OhXc3Zb9FBh1AuYzRTgZp.jpg',
        },
        {
          title: 'Favorite road trips',
          src: 'https://www.themoviedb.org/t/p/w440_and_h660_face/kEl2t3OhXc3Zb9FBh1AuYzRTgZp.jpg',
        },
        {
          title: 'Best airlines',
          src: 'https://www.themoviedb.org/t/p/w440_and_h660_face/kEl2t3OhXc3Zb9FBh1AuYzRTgZp.jpg',
        },
        {
          title: 'Pre-fab homes 2',
          src: 'https://www.themoviedb.org/t/p/w440_and_h660_face/kEl2t3OhXc3Zb9FBh1AuYzRTgZp.jpg',
        },
        {
          title: 'Favorite road trips 2',
          src: 'https://www.themoviedb.org/t/p/w440_and_h660_face/kEl2t3OhXc3Zb9FBh1AuYzRTgZp.jpg',
        },
        {
          title: 'Best airlines 2',
          src: 'https://www.themoviedb.org/t/p/w440_and_h660_face/kEl2t3OhXc3Zb9FBh1AuYzRTgZp.jpg',
        },
      ]
    }, 3000)
  },
}
</script>
