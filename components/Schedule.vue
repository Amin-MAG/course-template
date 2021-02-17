<template>
  <v-row class="fill-height">
    <v-col>
      <v-sheet class="mb-2" height="64">
        <v-toolbar class="d-flex flex-column align-center justify-center" flat>
          <v-btn
            v-if="this.$vuetify.breakpoint.name==='xs'"
            outlined
            x-small
            style="position:fixed; left: 0"
            color="grey darken-2"
            @click="setToday">
            Today
          </v-btn>
          <v-btn
            v-else
            outlined
            x-small
            style="position:fixed; left: 0"
            color="grey darken-2"
            @click="setToday">
            Today
          </v-btn>

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

          <v-toolbar-title :class="`text-center mx-2 ${textSize.month}`" v-if="$refs.calendar">
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

      <v-sheet class="mb-8" height="600">
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
    data: () => ({
      focus: '',
    }),
    mounted() {
      this.$refs.calendar.checkChange();
      this.setToday();
    },
    computed: {
      textSize() {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs':
            return {
              month: 'text-caption',
            };
          case 'sm':
            return {
              month: 'text-h6',
            };
          case 'md':
            return {
              month: 'text-h6',
            };
          case 'lg':
            return {
              month: 'text-h6',
            };
          case 'xl':
            return {
              month: 'text-h6',
            };
        }
      }
    },
    methods: {
      getEventColor(event) {
        return event.color
      },
      setToday() {
        this.focus = new Date()
      },
      prev() {
        this.$refs.calendar.prev()
      },
      next() {
        this.$refs.calendar.next()
      },
    },
    props: ['events']
  }
</script>

<style scoped>

</style>