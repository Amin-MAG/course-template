<template>
  <v-row justify="center" align="center" class="mt-4">
    <v-col cols="1"/>
    <v-col cols="10" class="justify-center">
      <v-list v-if="assignments.length !== 0" subheader>
        <v-list-item
          v-for="(hw, index) in assignments"
          :style="index!==0 ? 'border-top: solid #E0E0E0 1px' : ''"
          :key="index">
          <v-list-item-avatar>
            <v-icon color="blue">mdi-book</v-icon>
          </v-list-item-avatar>
          <v-list-item-title :class="`${sizes.assignmentText}`" v-text="hw.name"/>
          <v-list-item-action>
            <v-btn text>
              <v-icon class="mr-2" color="green">mdi-download</v-icon>
            </v-btn>
          </v-list-item-action>
        </v-list-item>
      </v-list>
      <div v-else>
        <lottie :width="sizes.lottieSize" :title="'empty'" :options="searchingLottie"/>
        <div class="text-caption mt-n12 text-center">It is empty.</div>
      </div>
    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>
  import lottie from 'vue-lottie/src/lottie';
  import  * as  searchingLottie from '../static/lottie/searching.json'

  export default {
    name: "Assignments",
    components: {
      lottie
    },
    data: () => ({
      searchingLottie: { animationData: searchingLottie.default }
    }),
    computed: {
      sizes() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return {
              lottieSize: 300,
              assignmentText: 'text-caption',
            };
          case 'sm':
            return {
              lottieSize: 300,
              assignmentText: 'text-body-1',
            };
          case 'md':
            return {
              lottieSize: 300,
              assignmentText: 'text-body-1',
            };
          case 'lg':
            return {
              lottieSize: 300,
              assignmentText: 'text-body-1',
            };
          case 'xl':
            return {
              lottieSize: 300,
              assignmentText: 'text-body-1',
            };
        }
      }
    },
    props: ['assignments']
  }
</script>

<style scoped>

</style>
