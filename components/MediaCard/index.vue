<template>
  <div>
    <v-card v-if="loading" outlined>
      <v-skeleton-loader
        type="image"
        v-bind="{ aspectRatio: '2 / 3' }"
      ></v-skeleton-loader>
      <v-skeleton-loader type="table-tfoot"></v-skeleton-loader>
    </v-card>
    <v-card v-else>
      <v-img
        :aspect-ratio="2 / 3"
        :src="media.src"
        class="white--text align-end"
        gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
      >
        <v-card-title v-text="media.title"></v-card-title>
      </v-img>
      <v-card-actions>
        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn icon @click.stop="sheet = true">
          <v-icon>mdi-bookmark</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-share-variant</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-bottom-sheet v-model="sheet" :inset="true" scrollable>
      <v-card class="rounded-b-0 rounded-t-lg">
        <v-app-bar dense flat>
          <v-app-bar-nav-icon />
          <v-toolbar-title class="text-h6 pl-0"> RESIDENT EVIL: Infinite Darkness </v-toolbar-title>

          <v-spacer></v-spacer>

          <v-btn icon @click="sheet = false">
            <v-icon>mdi-close</v-icon>
          </v-btn>
        </v-app-bar>
        <div class="d-flex flex-no-wrap justify-start pa-4">
          <div class="mr-3 flex-shrink-0">
            <v-img
              :aspect-ratio="16 / 9"
              width="500"
              src="https://cdn.pixabay.com/photo/2020/06/24/19/12/cabbage-5337431_1280.jpg"
            ></v-img>
          </div>
          <div class="flex-grow-1">
            <v-card-title class="text-h5 pt-0"
              >RESIDENT EVIL: Infinite Darkness</v-card-title
            >
            <v-card-subtitle>2021 &nbsp; 18+ &nbsp; 1 Season</v-card-subtitle>
            <v-card-text
              >Lorem, ipsum dolor sit amet consectetur adipisicing elit. Aliquam
              tenetur impedit quam quo! Iusto tenetur ut quas quia doloribus
              necessitatibus ipsa soluta, nostrum, magnam itaque voluptatum
              architecto rerum modi laboriosam!</v-card-text
            >
            <v-card-actions>
              <v-btn depressed>
                <v-icon left>mdi-play</v-icon>
                Play
              </v-btn>
              <v-btn depressed>
                <v-icon left>mdi-plus</v-icon>
                My List
              </v-btn>
            </v-card-actions>
          </div>
        </div>
      </v-card>
    </v-bottom-sheet>
  </div>
</template>

<script>
export default {
  props: {
    loading: {
      type: Boolean,
      default: false,
    },
    media: {
      type: [Object, Boolean],
      default: false,
    },
  },
  data() {
    return {
      sheet: false,
    }
  },
}
</script>

<style></style>
