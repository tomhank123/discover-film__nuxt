<template>
  <div>
    <v-card v-if="loading" outlined>
      <v-list-item three-line>
        <v-list-item-content>
          <v-skeleton-loader type="paragraph"></v-skeleton-loader>
        </v-list-item-content>
        <v-skeleton-loader
          type="image"
          v-bind="{
            ...attrs,
            class: 'ma-5 mr-0',
            width: 80,
            height: 80,
          }"
        >
        </v-skeleton-loader>
      </v-list-item>

      <v-card-actions>
        <v-skeleton-loader
          v-bind="{
            ...attrs,
            class: 'rounded-pill mx-2',
          }"
          type="button"
        ></v-skeleton-loader>
      </v-card-actions>
    </v-card>
    <v-card v-else outlined>
      <v-list-item three-line>
        <v-list-item-content>
          <div class="text-overline mb-4">OVERLINE</div>
          <v-list-item-title class="text-h5 mb-1">
            Headline 5
          </v-list-item-title>
          <v-list-item-subtitle
            >Greyhound divisely hello coldly fonwderfully</v-list-item-subtitle
          >
        </v-list-item-content>

        <v-list-item-avatar tile size="80" color="grey">
          <v-img src="https://cdn.vuetifyjs.com/images/john.jpg"></v-img>
        </v-list-item-avatar>
      </v-list-item>

      <v-card-actions>
        <v-btn rounded depressed router :to="`/celebs/${celeb.id}`">
          More
        </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  props: {
    loading: {
      type: Boolean,
      default: false,
    },
    celeb: {
      type: [Object, Boolean],
      default: false,
    },
  },
  data() {
    return {
      attrs: {
        boilerplate: false,
      },
    }
  }
}
</script>

<style></style>
