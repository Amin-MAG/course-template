<template>
  <v-app>
    <v-main>
      <v-container :class="`${sizes.headingTopMargin}`">
        <nuxt/>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
  export default {
    computed: {
      sizes() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return {
              headingTopMargin: 'mt-0'
            };
          case 'sm':
            return {
              headingTopMargin: 'mt-2'
            };
          case 'md':
            return {
              headingTopMargin: 'mt-4'
            };
          case 'lg':
            return {
              headingTopMargin: 'mt-10'
            };
          case 'xl':
            return {
              headingTopMargin: 'mt-10'
            };
        }
      }
    }
  }
</script>
