<template>
  <v-app>
    <v-main>
      <v-container :class="`${sizes.headingTopMargin}`">
        <nuxt/>
        <Footer v-if="hasfooter"/>
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
              headingTopMargin: 'my-0'
            };
          case 'sm':
            return {
              headingTopMargin: 'my-2'
            };
          case 'md':
            return {
              headingTopMargin: 'my-4'
            };
          case 'lg':
            return {
              headingTopMargin: 'my-5'
            };
          case 'xl':
            return {
              headingTopMargin: 'my-5'
            };
        }
      },
      hasfooter(){
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return false;
          case 'sm':
            return false;
          case 'md':
            return true;
          case 'lg':
            return true;
          case 'xl':
            return true;
        }
      }
    }
  }
</script>
