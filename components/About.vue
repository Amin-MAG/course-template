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

        <v-col cols="4" class="justify-center">
          <div :class="`${textSize.charactersTitle} ${textSize.charactersTitleAlign}`">Professor</div>
          <div
            class="pa-4 d-flex flex-column align-center justify-center">
            <v-img
              class="rounded-circle"
              :width="(this.$vuetify.breakpoint.name==='xs') ? '100%' : '75%'"
              :src="people.professor.image"
              :alt="people.professor.name"/>
          </div>
          <div :class="`mt-2 text-center ${textSize.characters}`">
            {{people.professor.name}}
          </div>
        </v-col>

        <v-col cols="8">
          <div :class="`${textSize.charactersTitle} ${textSize.charactersTitleAlign}`">Teacher Assistants</div>
          <v-row>
            <v-col v-for="(ta, index) in people.assistants" :key="index" :cols="assistantsColumns"
                   class="justify-center">
              <div
                class="pa-4 d-flex flex-column align-center justify-center">
                <v-img
                  class="rounded-circle"
                  width="100%"
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
      assistantsColumns() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return 6;
          case 'sm':
            return 4;
          case 'md':
            return 4;
          case 'lg':
            return 3;
          case 'xl':
            return 3;
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
              characters: 'text-h7',
              charactersTitleAlign: ''
            };
          case 'lg':
            return {
              charactersTitle: 'text-h5',
              characters: 'text-h7',
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