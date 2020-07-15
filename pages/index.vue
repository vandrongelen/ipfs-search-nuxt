<template>
  <div>
    <v-parallax src="/background-02.png" class="parallax">
      <v-row align="end">
        <v-col class="white--text" justify="center">
          <h2 class="mr-3 text-center">
            DWEB <span>SEARCH</span>
          </h2>
          <p class="mb-2 text-center">
            Search the Distributed&#160;Web
          </p>
          <searchbar />
        </v-col>
      </v-row>
    </v-parallax>
  </div>
</template>

<script>
import Searchbar from '@/components/Searchbar.vue'

export default {
  components: {
    Searchbar
  }
}
</script>

<style lang="scss" scoped>
  .parallax {
    max-height: 50vh;
    background-color: darken(#0e3344, 0%);
    // background-color: #0e3344;
  }
  h2 {
    font-size: 200%;
    letter-spacing: 4px;
    font-weight: 500;
    span {
      letter-spacing: 4px;
      font-weight: 300;
    }
  }
  p {
    color: #00bcd4;
  }
</style>
