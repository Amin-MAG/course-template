<template>
  <v-row justify="center" align="center">
    <v-col cols="1"/>
    <v-col cols="10" class="justify-center">

      <div class="pa-5">
        <div class="text-center text-h1 pa-2">{{course.title}}</div>
        <div class="text-center text-h4 blue-grey--text mt-4">{{course.subtitle}}</div>
      </div>


      <div
        class="d-flex align-center justify-center">

        <v-btn
          v-for="(item, index) in menu"
          :key="index"
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
      <assignments v-show="page===PROJECT_PAGE" :assignments="projects"/>
      <CourseMaterials v-show="page===COURSE_MATERIAL_PAGE" :materials="materials"/>
      <Schedule v-show="page===SCHEDULE_PAGE" :events="schedule.events"/>

      <v-divider class="my-8"/>

      <Footer/>

    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>

  import About from "../components/About";
  import Footer from "../components/Footer";
  import CourseMaterials from "../components/CourseMaterials";
  import Schedule from "../components/Schedule";

  const HOME_PAGE = 'home';
  const SCHEDULE_PAGE = 'schedule';
  const ASSIGNMENT_PAGE = 'assignments';
  const PROJECT_PAGE = 'projects';
  const COURSE_MATERIAL_PAGE = 'materials';

  const MALE_PROFILE = require('../static/images/profile-boy.jpg');
  const FEMALE_PROFILE = require('../static/images/profile-girl.jpg');
  const REF_BOOK_1 = require('../static/images/ref_book1.jpg');
  const REF_BOOK_2 = require('../static/images/ref_book2.jpg');

  export default {
    computed: {
      HOME_PAGE: () => HOME_PAGE,
      SCHEDULE_PAGE: () => SCHEDULE_PAGE,
      ASSIGNMENT_PAGE: () => ASSIGNMENT_PAGE,
      PROJECT_PAGE: () => PROJECT_PAGE,
      COURSE_MATERIAL_PAGE: () => COURSE_MATERIAL_PAGE,
    },
    data: () => ({
      page: SCHEDULE_PAGE,

      // Course Details
      course: {
        title: "Course Name",
        subtitle: "More Details about course"
      },

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

      // Schedule
      schedule: {
        events: [
          {
            name: 'Event 1',
            start: '2021-02-01 12:30',
            end: '2021-02-09 15:30',
            color: 'red'
          },
          {
            name: 'Event 2',
            start: '2021-02-09 12:30',
            end: '2021-02-19 15:30',
            color: 'indigo'
          },
          {
            name: 'Event 3',
            start: '2021-02-09 12:30',
            end: '2021-02-15 15:30',
            color: 'green'
          },
          {
            name: 'Event 4',
            start: '2021-02-20 12:30',
            end: '2021-02-24 15:30',
            color: 'blue'
          },
        ]
      },

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

      // Projects
      projects: [
        {
          name: "Project number 1",
          file: ''
        },
        {
          name: "Project number 2",
          file: ''
        },
        {
          name: "Project number 3",
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
        ],
      },

      // References
      materials: {
        main: [
          {
            name: "Reference 1",
            description: "This book is Reference 1",
            cover: REF_BOOK_1,
          },
          {
            name: "Reference 2",
            description: "This book is Reference 2",
            cover: REF_BOOK_2,
          }
        ],
        additional: [
          {
            name: "Reference 1",
            description: "This book is Reference 1",
            cover: REF_BOOK_2,
          },
          {
            name: "Reference 2",
            description: "This book is Reference 2",
            cover: REF_BOOK_1,
          },
          {
            name: "Reference 3",
            description: "This book is Reference 3",
            cover: REF_BOOK_2,
          },
          {
            name: "Reference 4",
            description: "This book is Reference 4",
            cover: REF_BOOK_1,
          }
        ]
      }
    }),
    components: { Schedule, CourseMaterials, Footer, About },
  }
</script>
