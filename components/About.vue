<template>
  <v-row justify="center" align="center" class="mt-4">
    <v-col cols="1"/>
    <v-col cols="10" class="justify-center">

      <v-alert
        dense
        outlined
        type="info">
        <strong>Announcements:</strong>
        <br style="clear: both">
        <ul>
          <li>Announcement 1</li>
          <li>Announcement 2</li>
          <li>Announcement 3</li>
        </ul>
      </v-alert>

      <div class="mt-6">
        <div class="text-h5">Course Description</div>
        <div class="mt-2 text-body-1">In higher education in various countries, such as Canada, Israel, Nigeria and
          the United States, a course is a unit of teaching that typically lasts one academic term, is led by one or
          more instructors, and has a fixed roster of students. A course usually covers an individual subject.
        </div>
      </div>


      <v-row class="mt-4">

        <v-col cols="4" class="justify-center">
          <div class="text-h5">Professor</div>
          <div
            class="pa-4 d-flex flex-column align-center justify-center">
            <v-img
              class="rounded-circle"
              width="75%"
              :src="people.professor.image"
              :alt="people.professor.name"/>
          </div>
          <div class="mt-2 text-center text-h6">
            {{people.professor.name}}
          </div>
        </v-col>

        <v-col cols="8">
          <div class="text-h5">Teacher Assistants</div>
          <v-row>
            <v-col v-for="(ta, index) in people.assistants" :key="index" cols="3" class="justify-center">
              <div
                class="pa-4 d-flex flex-column align-center justify-center">
                <v-img
                  class="rounded-circle"
                  width="100%"
                  :src="ta.image"
                  :alt="ta.name"/>
              </div>
              <div class="mt-2 text-center text-h7">
                {{ta.name}}
              </div>
            </v-col>
          </v-row>
        </v-col>


      </v-row>

    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>
  export default {
    name: "Homepage",
    props: ['people']
  }
</script>

<style scoped>

</style>