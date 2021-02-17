<template>
  <v-row class="fill-height">
    <v-col>
      <v-sheet class="mb-2" height="64">
        <v-toolbar class="d-flex flex-column align-center justify-center" flat>
          <v-btn
            fab
            text
            small
            class="mx-2"
            color="grey darken-2"
            @click="prev">
            <v-icon small>
              mdi-chevron-left
            </v-icon>
          </v-btn>

          <v-toolbar-title class="text-center mx-2 text-h6" v-if="$refs.calendar">
            {{ $refs.calendar.title }}
          </v-toolbar-title>

          <v-btn
            fab
            text
            small
            class="mx-2"
            color="grey darken-2"
            @click="next">
            <v-icon small>
              mdi-chevron-right
            </v-icon>
          </v-btn>

          <v-spacer/>
        </v-toolbar>
      </v-sheet>

      <div class="mb-6 d-flex flex-column align-center justify-center">
        <v-btn
          outlined
          class="mx-auto"
          color="grey darken-2"
          @click="setToday">
          Today
        </v-btn>

      </div>

      <v-sheet height="600">
        <v-calendar
          ref="calendar"
          v-model="focus"
          color="primary"
          type="month"
          :events="events"
          :event-color="getEventColor"/>
      </v-sheet>
    </v-col>
  </v-row>
</template>

<script>
  export default {
    name: "Schedule",
    data: ()=>({
      focus: '',
    }),
    mounted () {
      this.$refs.calendar.checkChange();
    },
    methods: {
      getEventColor(event) {
        return event.color
      },
      setToday() {
        this.focus = ''
      },
      prev() {
        this.$refs.calendar.prev()
      },
      next() {
        this.$refs.calendar.next()
      },
      rnd(a, b) {
        return Math.floor((b - a + 1) * Math.random()) + a
      },
    },
    props: ['events']
  }
</script>

<style scoped>

</style>