<template>
  <v-row justify="center" align="center" class="mt-4">
    <v-col lg="1" xl="1" md="1" cols="0"/>
    <v-col lg="10" xl="10" md="10" cols="12" class="justify-center">

      <v-alert
        dense
        outlined
        type="info">
        <strong>Announcements:</strong>
        <br style="clear: both">
        <ul>
          <li>Welcome !!</li>
          <!--          <li>Announcement 2</li>-->
          <!--          <li>Announcement 3</li>-->
        </ul>
      </v-alert>

      <div class="mt-6">
        <div class="text-h5">Course Description</div>
        <div class="mt-2 text-body-1">
          {{courseDescription}}
        </div>
      </div>


      <v-row class="mt-4">

        <v-col :cols="12-columns.assistants-columns.distance" class="justify-center">
          <div :class="`${textSize.charactersTitle} ${textSize.charactersTitleAlign}`">Instructor</div>
          <div
            class="pa-2 d-flex flex-column align-center justify-center">
            <v-img
              class="rounded-circle"
              width="100%"
              :src="people.professor.image"
              aspect-ratio="1"
              :alt="people.professor.name"/>
          </div>
          <div :class="`mt-2 text-center ${textSize.characters}`">
            {{people.professor.name}}
          </div>
        </v-col>

        <v-col v-if="columns.distance!==0" :cols="columns.distance"/>


        <v-col :cols="columns.assistants">
          <div :class="`${textSize.charactersTitle} ${textSize.charactersTitleAlign}`">Teaching Assistants</div>
          <v-row>
            <v-col v-for="(ta, index) in people.assistants" :key="index" :cols="columns.assistant"
                   class="justify-center">
              <div
                class="pa-2 d-flex flex-column align-center justify-center">
                <v-img
                  class="rounded-circle"
                  width="100%"
                  aspect-ratio="1"
                  :src="ta.image"
                  :alt="ta.name"/>
              </div>
              <div :class="`mt-2 text-center ${textSize.characters}`">
                {{ta.name}}
              </div>
            </v-col>
          </v-row>
        </v-col>


      </v-row>

    </v-col>
    <v-col lg="1" xl="1" md="1" cols="0"/>
  </v-row>
</template>

<script>
  export default {
    name: "Homepage",
    computed: {
      columns() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return {
              assistants: 8,
              assistant: 6,
              distance: 0,
            };
          case 'sm':
            return {
              assistants: 9,
              assistant: 4,
              distance: 0,
            };
          case 'md':
            return {
              assistants: 9,
              assistant: 4,
              distance: 0,
            };
          case 'lg':
            return {
              assistants: 8,
              assistant: 3,
              distance: 2,
            };
          case 'xl':
            return {
              assistants: 8,
              assistant: 3,
              distance: 2,
            };
        }
      },
      textSize() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return {
              charactersTitle: 'text-h8',
              characters: 'text-caption',
              charactersTitleAlign: 'text-center'
            };
          case 'sm':
            return {
              charactersTitle: 'text-h8',
              characters: 'text-caption',
              charactersTitleAlign: 'text-center'
            };
          case 'md':
            return {
              charactersTitle: 'text-h5',
              characters: 'text-caption',
              charactersTitleAlign: ''
            };
          case 'lg':
            return {
              charactersTitle: 'text-h5',
              characters: 'text-caption',
              charactersTitleAlign: ''
            };
          case 'xl':
            return {
              charactersTitle: 'text-h5',
              characters: 'text-h7',
              charactersTitleAlign: ''
            };
        }
      }
    },
    props: ['people', 'courseDescription']
  }
</script>

<style scoped>

</style>
