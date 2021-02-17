<template>
  <v-row justify="center" align="center">
    <v-col cols="1"/>
    <v-col cols="10" class="justify-center">

      <div class="pa-5">
        <div class="text-center text-h1 pa-2">Course Name</div>
        <div class="text-center text-h4 blue-grey--text mt-4">More Details about course</div>
      </div>

      <v-btn-toggle
        v-model="page"
        tile
        style="width: 100%"
        class="justify-center"
        color="light-blue darken-2"
        group>

        <v-btn value="home">
          Home
        </v-btn>

        <v-btn value="schedule">
          Schedule
        </v-btn>

        <v-btn value="assignments">
          Assignments
        </v-btn>

        <v-btn value="projects">
          Projects
        </v-btn>

        <v-btn value="course-materials">
          Course Materials
        </v-btn>

      </v-btn-toggle>

      <v-divider/>


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
                <v-col v-for="ta in people.assistants" cols="3" class="justify-center">
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

      <v-divider class="my-8"/>

      <v-row>
        <v-col cols="4"/>
        <v-col class="text-center" cols="4">
          2021
        </v-col>
        <v-col cols="4"/>
      </v-row>


    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>

  const MALE_PROFILE = require('../static/images/profile-boy.jpg');
  const FEMALE_PROFILE = require('../static/images/profile-girl.jpg');

  export default {
    data: () => ({
      page: "home",

      people: {
        professor: {
          name: "Professor",
          image: MALE_PROFILE
        },
        assistants: [
          {
            name: "Assistant 1",
            image: MALE_PROFILE
          },
          {
            name: "Assistant 2",
            image: MALE_PROFILE
          },
          {
            name: "Assistant 3",
            image: FEMALE_PROFILE
          },
          {
            name: "Assistant 4",
            image: FEMALE_PROFILE
          },
          {
            name: "Assistant 5",
            image: MALE_PROFILE
          },
          {
            name: "Assistant 6",
            image: FEMALE_PROFILE
          },
          {
            name: "Assistant 7",
            image: MALE_PROFILE
          },
          {
            name: "Assistant 8",
            image: MALE_PROFILE
          },
          {
            name: "Assistant 9",
            image: FEMALE_PROFILE
          },
          {
            name: "Assistant 10",
            image: MALE_PROFILE
          }
        ]
      }
    }),
    components: {}
  }
</script>
