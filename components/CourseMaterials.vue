<template>
  <v-row justify="center" align="center" class="mt-4">
    <v-col cols="1"/>
    <v-col cols="10" class="justify-center">
      <div class="text-h4">Main Book</div>
      <v-row class="my-4">
        <v-col
          v-for="(material, index) in materials.main"
          :key="index"
          cols="4">
          <v-card>
            <v-img :src="material.cover"/>
            <v-card-title>{{material.name}}</v-card-title>
            <v-card-text>
              <div>{{material.description}}</div>
            </v-card-text>
            <v-card-actions>
              <v-spacer/>
              <v-btn text>
                <v-icon class="mr-2" color="green">mdi-download</v-icon>
                Download
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>


      <div class="text-h4 mt-8">Additional Resources</div>
      <v-row class="my-4">
        <v-col
          v-for="(material, index) in materials.additional"
          :key="index"
          cols="4">
          <v-card>
            <v-img
              :src="material.cover"/>
            <v-card-title>{{material.name}}</v-card-title>
            <v-card-text>
              <div>{{material.description}}</div>
            </v-card-text>
            <v-card-actions>
              <v-spacer/>
              <v-btn text>
                <v-icon class="mr-2" color="green">mdi-download</v-icon>
                Download
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-col>
    <v-col cols="1"/>
  </v-row>
</template>

<script>
  export default {
    name: "CourseMaterials",
    props: ['materials']
  }
</script>

<style scoped>

</style>