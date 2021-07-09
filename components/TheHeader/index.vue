<template>
  <v-app-bar :dense="true" app>
    <v-btn text href="/">
      <the-logo />
    </v-btn>
    <div>
      <v-btn
        v-for="{ text, slug } in links"
        :key="slug"
        text
        rounded
        router
        exact
        :to="slug"
      >
        {{ text }}
      </v-btn>
    </div>
    <v-spacer />
    <v-chip pill color="cyan" class="darken-3 mr-3">
      <v-avatar left>
        <v-img src="https://cdn.vuetifyjs.com/images/john.jpg"></v-img>
      </v-avatar>
      Duc Tran
    </v-chip>
    <v-menu
      :close-on-content-click="false"
      :nudge-width="200"
      offset-x
      offset-y
    >
      <template #activator="{ on, attrs }">
        <v-btn icon v-bind="attrs" v-on="on">
          <v-icon>mdi-chevron-down</v-icon>
        </v-btn>
      </template>

      <v-card>
        <v-list>
          <v-list-item>
            <v-list-item-avatar>
              <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title>Duc Tran</v-list-item-title>
              <v-list-item-subtitle>Founder of Vuetify</v-list-item-subtitle>
            </v-list-item-content>

            <v-list-item-action>
              <v-btn :class="fav ? 'cyan--text' : ''" icon @click="fav = !fav">
                <v-icon>mdi-heart</v-icon>
              </v-btn>
            </v-list-item-action>
          </v-list-item>
        </v-list>

        <v-divider></v-divider>
        <v-list>
          <v-list-item>
            <v-btn large text rounded block class="justify-start">
              <v-icon left> mdi-information-outline </v-icon>
              Give Feedback
            </v-btn>
          </v-list-item>
        </v-list>
        <v-divider></v-divider>
        <v-list>
          <v-list-item>
            <v-btn
              large
              text
              rounded
              block
              class="justify-start"
              @click="reveal = true"
            >
              <v-icon left> mdi-earth </v-icon>
              Display & Accessibility
            </v-btn>
          </v-list-item>
          <v-list-item>
            <v-btn large text rounded block class="justify-start">
              <v-icon left> mdi-cog </v-icon>
              Setting
            </v-btn>
          </v-list-item>
          <v-list-item>
            <v-btn large text rounded block class="justify-start">
              <v-icon left> mdi-logout-variant </v-icon>
              Sign Out
            </v-btn>
          </v-list-item>
        </v-list>
        <v-expand-transition>
          <v-card
            v-if="reveal"
            class="transition-fast-in-fast-out v-card--reveal"
            style="height: 100%"
          >
            <v-toolbar dense flat>
              <v-btn icon @click="reveal = false">
                <v-icon>mdi-arrow-left</v-icon>
              </v-btn>
              <v-toolbar-title>Display & Accessibility</v-toolbar-title>
            </v-toolbar>
            <v-list>
              <v-list-item>
                <v-list-item-action>
                  <v-switch
                    v-model="$vuetify.theme.dark"
                    :inset="false"
                    color="cyan"
                  ></v-switch>
                </v-list-item-action>
                <v-list-item-title>Dark Mode</v-list-item-title>
              </v-list-item>
              <v-list-item>
                <v-list-item-action>
                  <v-switch
                    color="cyan"
                    @change="$vuetify.lang.current = 'vi'"
                  ></v-switch>
                </v-list-item-action>
                <v-list-item-title>Vietnamese</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-card>
        </v-expand-transition>
      </v-card>
    </v-menu>
  </v-app-bar>
</template>

<script>
export default {
  data() {
    return {
      fav: true,
      menu: false,
      reveal: false,
      links: [
        {
          text: 'TV Shows',
          slug: '/tv-shows',
        },
        {
          text: 'Movies',
          slug: '/movies',
        },
        {
          text: 'Celebs',
          slug: '/celebs',
        },
      ],
    }
  }
}
</script>

<style>
.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
}
</style>
