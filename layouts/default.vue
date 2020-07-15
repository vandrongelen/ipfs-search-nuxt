<template>
  <v-app dark hidden>
    <v-main>
      <v-container class="fluid pa-0">
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  $el: '#app',

  // eslint-disable-next-line
  mounted:function(){this.$nextTick(function(){
    this.$el.removeAttribute('hidden')
  })
  }
}
</script>

<style lang="scss" scoped>
  .fluid {
    max-width: 100%;
  }
</style>
