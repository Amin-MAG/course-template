<template>
  <v-row justify="center" align="center" class="mt-4">
    <v-col cols="1"/>
    <v-col cols="10" class="justify-center">
      <v-list subheader>
        <v-list-item
          v-for="(hw, index) in assignments"
          :style="index!==0 ? 'border-top: solid #E0E0E0 1px' : ''"
          :key="index">
          <v-list-item-avatar>
            <v-icon color="blue">mdi-book</v-icon>
          </v-list-item-avatar>
          <v-list-item-title :class="`${textSize.assignmentText}`" v-text="hw.name"/>
          <v-list-item-action>
            <v-btn text>
              <v-icon class="mr-2" color="green">mdi-download</v-icon>
            </v-btn>
          </v-list-item-action>
        </v-list-item>
      </v-list>
    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>
  export default {
    name: "Assignments",
    computed: {
      textSize() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return {
              assignmentText: 'text-caption',
            };
          case 'sm':
            return {
              assignmentText: 'text-body-1',
            };
          case 'md':
            return {
              assignmentText: 'text-body-1',
            };
          case 'lg':
            return {
              assignmentText: 'text-body-1',
            };
          case 'xl':
            return {
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