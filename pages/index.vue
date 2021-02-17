<template>
  <v-row justify="center" align="center">
    <v-col cols="1"/>
    <v-col cols="10" class="justify-center">

      <div class="pa-5">
        <div class="text-center text-h1 pa-2">Course Name</div>
        <div class="text-center text-h4 blue-grey--text mt-4">More Details about course</div>
      </div>


      <div
        class="d-flex align-center justify-center">

        <v-btn
          v-for="item in menu"
          color="black"
          v-ripple="{ class: `light-blue--text` }"
          :style="page===item.pageName ? 'background-color: #B3E5FC' : ''"
          @click="page=item.pageName"
          tile
          text
          large>
          {{item.text}}
        </v-btn>

      </div>


      <v-divider/>

      <about v-show="page===HOME_PAGE" :people="people"/>
      <assignments v-show="page===ASSIGNMENT_PAGE" :assignments="assignments"/>

      <v-divider class="my-8"/>

      <Footer/>

    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>

  import About from "../components/About";
  import Footer from "../components/Footer";

  const HOME_PAGE = 'home';
  const ASSIGNMENT_PAGE = 'assignments';

  const MALE_PROFILE = require('../static/images/profile-boy.jpg');
  const FEMALE_PROFILE = require('../static/images/profile-girl.jpg');

  export default {
    computed: {
      HOME_PAGE: () => HOME_PAGE,
      ASSIGNMENT_PAGE: () => ASSIGNMENT_PAGE,
    },
    data: () => ({
      page: ASSIGNMENT_PAGE,

      // Main Menu
      menu: [
        {
          pageName: HOME_PAGE,
          text: "Home"
        },
        {
          pageName: "schedule",
          text: "Schedule"
        },
        {
          pageName: "assignments",
          text: "Assignments"
        },
        {
          pageName: "projects",
          text: "Projects"
        },
        {
          pageName: "materials",
          text: "Course Materials"
        },
      ],

      // Assignments
      assignments: [
        {
          name: "Assignment number 1",
          file: ''
        },
        {
          name: "Assignment number 2",
          file: ''
        },
        {
          name: "Assignment number 3",
          file: ''
        },
        {
          name: "Assignment number 4",
          file: ''
        },
        {
          name: "Assignment number 5",
          file: ''
        }
      ],

      // Characters
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
    components: { Footer, About }
  }
</script>
