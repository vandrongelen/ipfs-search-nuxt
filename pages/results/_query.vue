<template>
  <div>
    <v-app-bar color="#0e3344">
      <v-row>
        <v-col cols="12">
          <searchbar />
        </v-col>
      </v-row>
    </v-app-bar>

    <v-container>
      <v-row>
        <v-col cols="12" align="end" class="text--secondary body-2">
          Filters:
          <span>
            <v-menu>
              <template v-slot:activator="{ on }">
                <span class="pt-2" v-on="on">
                  Size {{ sizeFilter }}<v-icon small>mdi-menu-down</v-icon>
                </span>
              </template>
              <v-list>
                <v-list-item
                  v-for="(item, index) in sizeItems"
                  :key="index"
                  @click="setSizeFilter(index)"
                >
                  <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </span>

          <span>
            <v-menu>
              <template v-slot:activator="{ on }">
                <span class="pt-2" v-on="on">
                  Last seen {{ lastSeenFilter }}
                  <v-icon small>
                    mdi-menu-down
                  </v-icon>
                </span>
              </template>
              <v-list>
                <v-list-item
                  v-for="(item, index) in lastSeenItems"
                  :key="index"
                  @click="setLastSeenFilter(index)"
                >
                  <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </span>
        </v-col>
      </v-row>
    </v-container>

    <v-container>
      <v-row dense>
        <v-col cols="12">
          <v-subheader class="mt-n2 mb-n4">
            Texts (230) - view all
          </v-subheader>
        </v-col>
      </v-row>
      <v-row dense>
        <v-col cols="12">
          <v-card>
            <v-card-title class="subtitle-1">
              Unlimited music now
            </v-card-title>
            <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-card>
            <v-card-title class="subtitle-1">
              Unlimited music now
            </v-card-title>
            <v-card-subtitle>
              Listen to your favorite artists and albums whenever and wherever, online and offline.
            </v-card-subtitle>
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-card>
            <v-card-title class="subtitle-1">
              Unlimited music now
            </v-card-title>
            <v-card-subtitle>Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>
            <!-- <v-card-actions>
              <v-btn text>Listen Now</v-btn>
            </v-card-actions> -->
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-subheader class="mt-n2 mb-n4" />
        </v-col>
      </v-row>

      <v-row dense>
        <v-col cols="12">
          <v-subheader class="mt-n2 mb-n4">
            Audio (40)
          </v-subheader>
        </v-col>
      </v-row>
      <v-row dense>
        <v-col cols="12">
          <v-card>
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title
                  class="subtitle-1"
                >
                  Supermodel
                </v-card-title>
                <v-card-subtitle>Foster the People</v-card-subtitle>
              </div>
              <v-avatar
                class="ma-2"
                size="125"
                tile
              >
                <v-img src="https://cdn.vuetifyjs.com/images/cards/halcyon.png" />
              </v-avatar>
            </div>
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-card>
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title
                  class="subtitle-1"
                >
                  Halcyon Days
                </v-card-title>
                <v-card-subtitle>Ellie Goulding</v-card-subtitle>
              </div>

              <v-avatar
                class="ma-2"
                size="125"
                tile
              >
                <v-img src="https://cdn.vuetifyjs.com/images/cards/foster.jpg" />
              </v-avatar>
            </div>
          </v-card>
        </v-col>
        <v-col cols="12">
          <v-card>
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title
                  class="subtitle-1"
                >
                  Supermodel
                </v-card-title>
                <v-card-subtitle>Foster the People</v-card-subtitle>
              </div>
              <v-avatar
                class="ma-2"
                size="125"
                tile
              >
                <v-img src="https://cdn.vuetifyjs.com/images/cards/halcyon.png" />
              </v-avatar>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Searchbar from '@/components/Searchbar.vue'
export default {
  components: {
    Searchbar
  },

  data: () => ({
    sizeFilter: '0-10mb',
    lastSeenFilter: '<3hr',

    sizeItems: [
      { title: '0-10mb' },
      { title: '10-100mb' },
      { title: '100mb-1gb' },
      { title: '1gb+' }
    ],

    lastSeenItems: [
      { title: '<3hr' },
      { title: '<24hr' },
      { title: '<7d' }
    ]
  }),

  methods: {
    setSizeFilter (index) {
      this.sizeFilter = this.sizeItems[index].title
    },

    setLastSeenFilter (index) {
      this.lastSeenFilter = this.lastSeenItems[index].title
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
