<template>
  <section>
    <v-container>
      <v-row class="my-5">
        <v-col cols="8">
          <v-row>
            <v-col v-for="card in cards" :key="card.title" cols="3">
              <v-card>
                <v-img
                  :src="card.src"
                  class="white--text align-end"
                  gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                >
                  <v-card-title v-text="card.title"></v-card-title>
                </v-img>

                <v-card-actions>
                  <v-spacer></v-spacer>

                  <v-btn icon>
                    <v-icon>mdi-heart</v-icon>
                  </v-btn>

                  <v-btn icon>
                    <v-icon>mdi-bookmark</v-icon>
                  </v-btn>

                  <v-btn icon>
                    <v-icon>mdi-share-variant</v-icon>
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="4">
          <v-card tile>
            <v-img
              height="200px"
              src="https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg"
            >
              <v-app-bar flat color="rgba(0, 0, 0, 0)">
                <v-app-bar-nav-icon color="white"></v-app-bar-nav-icon>

                <v-toolbar-title class="text-h6 white--text pl-0">
                  Messages
                </v-toolbar-title>

                <v-spacer></v-spacer>

                <v-btn color="white" icon>
                  <v-icon>mdi-dots-vertical</v-icon>
                </v-btn>
              </v-app-bar>

              <v-card-title class="white--text mt-8">
                <v-avatar size="56">
                  <img
                    alt="user"
                    src="https://cdn.vuetifyjs.com/images/john.jpg"
                  />
                </v-avatar>
                <p class="ml-3">John Doe</p>
              </v-card-title>
            </v-img>

            <v-card-title>Cafe Badilico</v-card-title>

            <v-card-text>
              <v-row align="center" class="mx-0">
                <v-rating
                  :value="4.5"
                  color="amber"
                  dense
                  half-increments
                  readonly
                  size="14"
                ></v-rating>

                <div class="grey--text ms-4">4.5 (413)</div>
              </v-row>

              <div class="my-4 text-subtitle-1">$ • Italian, Cafe</div>

              <div>
                Small plates, salads & sandwiches - an intimate setting with 12
                indoor seats plus patio seating.
              </div>
            </v-card-text>

            <v-divider class="mx-4"></v-divider>

            <v-card-title>Tonight's availability</v-card-title>

            <v-card-text>
              <v-chip-group
                v-model="selection"
                active-class="cyan darken-3 white--text"
                column
              >
                <v-chip>
                  <v-icon left>mdi-share-variant</v-icon>
                  Share
                </v-chip>
                <v-chip>
                  <v-icon left>mdi-heart</v-icon>
                  Follow me
                </v-chip>
              </v-chip-group>
            </v-card-text>

            <v-card-actions>
              <v-btn color="cyan darken-3" text @click="reserve">
                Reserve
              </v-btn>
            </v-card-actions>

            <v-card-text>
              <div class="font-weight-bold ml-8 mb-2">More Info</div>

              <v-timeline align-top dense>
                <v-timeline-item
                  v-for="message in messages"
                  :key="message.time"
                  :color="message.color"
                  small
                >
                  <div>
                    <div class="font-weight-normal">
                      <strong>{{ message.from }}</strong> @{{ message.time }}
                    </div>
                    <div>{{ message.message }}</div>
                  </div>
                </v-timeline-item>
              </v-timeline>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  data: () => ({
    messages: [
      {
        from: 'You',
        message: `Sure, I'll see you later.`,
        time: '10:42am',
        color: 'cyan darken-3',
      },
      {
        from: 'John Doe',
        message: 'Yeah, sure. Does 1:00pm work?',
        time: '10:37am',
        color: 'cyan darken-3',
      },
      {
        from: 'You',
        message: 'Did you still want to grab lunch today?',
        time: '9:47am',
        color: 'cyan darken-3',
      },
    ],
    cards: [
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
    ],
  }),
}
</script>
