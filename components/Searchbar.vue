<template>
  <div>
    <v-container class="d-flex justify-center">
      <div class="search flex-grow-1">
        <v-text-field
          v-model="query"
          placeholder="Search"
          light
          rounded
          autofocus
          solo
          validate-on-blur
          hide-details
          @keyup.enter="onClickSearch"
        >
          <template v-slot:append>
            <v-menu
              style="top: -12px"
              offset-y
            >
              <template v-slot:activator="{ on }">
                <div class="pt-1 grey--text" v-on="on">
                  {{ contentType }}
                  <v-icon>
                    mdi-menu-down
                  </v-icon>
                </div>
              </template>
              <v-list>
                <v-list-item

                  v-for="(item, index) in items"
                  :key="index"
                  @click="showSelectedContentType(index)"
                >
                  <v-list-item-title>{{ item.title }}</v-list-item-title>
                </v-list-item>
              </v-list>
            </v-menu>
          </template>
          <template v-slot:append-outer>
            <v-tooltip>
              <template v-slot:activator="{ on }">
                <v-icon
                  class="mt-n1"
                  large
                  color="white"
                  v-on="on"
                >
                  mdi-magnify
                </v-icon>
              </template>
            </v-tooltip>
          </template>
        </v-text-field>
      </div>
    </v-container>
  </div>
</template>

<script>
export default {

  data: () => ({
    query: null,
    previousQuery: null,
    contentType: 'Any file',
    items: [
      { title: 'Any file' },
      { title: 'Texts' },
      { title: 'Images' },
      { title: 'Music' },
      { title: 'Videos' },
      { title: 'Directories' }
    ]
  }),

  methods: {
    showSelectedContentType (index) {
      console.log(index); // eslint-disable-line
      this.contentType = this.items[index].title
    },

    onClickSearch () {
      if (this.previousQuery !== this.query) {
        this.$router.push({ path: `/results/${this.query}` })
      }
      this.previousQuery = this.query
    },

    watchRouter () {
      if (this.$route.name === 'home') {
        this.query = ''
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .search {
    max-width: 768px;
  }
</style>
