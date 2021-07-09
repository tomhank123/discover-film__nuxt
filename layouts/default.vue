<template>
  <v-app dark>
    <the-header />
    <v-main>
      <Nuxt />
    </v-main>
    <the-footer />
  </v-app>
</template>

<script>
export default {
  scrollToTop: true,
  data() {
    return {}
  },
}
</script>
