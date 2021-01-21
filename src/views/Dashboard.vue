<template>
  <!-- <v-layout row justify-start class="mb-3">
        <v-btn small flat color="grey" @click="sortBy('title')">
          <v-icon small left>folder</v-icon>
          <span class="caption text-lowercase">By project name</span>
        </v-btn>
        <v-btn small flat color="grey" @click="sortBy('person')">
          <v-icon small left>person</v-icon>
          <span class="caption text-lowercase">By Person</span>
        </v-btn>
      </v-layout> -->

  <v-container class="my-5">
    <v-row class="pa-3 mb-2">
      <v-btn small class="grey--text">
        <v-icon small left>mdi-folder</v-icon>
        <span class="caption text-lowercase">By project name</span>
      </v-btn>
      <v-btn small class="grey--text ml-2">
        <v-icon small left>mdi-account</v-icon>
        <span class="caption text-lowercase">By person</span>
      </v-btn>
    </v-row>

    <v-card v-for="project in projects" :key="project.title" class="px-3">
      <v-row class="pa-1 my-2" :class="`project ${project.status}`">
        <v-col cols="12" md="6">
          <div class="caption grey--text">Project Title</div>

          <div>{{ project.title }}</div>
        </v-col>

        <v-col xs="2">
          <div class="caption grey--text">Person</div>

          <div>{{ project.person }}</div>
        </v-col>

        <v-col xs="2">
          <div class="caption grey--text">Due Date</div>

          <div>{{ project.due }}</div>
        </v-col>

        <v-col xs="2">
          <div class="text-center">
            <v-chip :class="`mt-2 ${project.status}`">
              {{ project.status }}
            </v-chip>
          </div>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Design a new website",
          person: "Evan",
          due: "1st Jan 2019",
          status: "ongoing",
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!",
        },
        {
          title: "Code up the homepage",
          person: "tanvir",
          due: "10th Jan 2019",
          status: "complete",
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!",
        },
        {
          title: "Design video thumbnails",
          person: "Asif",
          due: "20th Dec 2018",
          status: "complete",
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!",
        },
        {
          title: "Create a community forum",
          person: "Mou",
          due: "20th Oct 2018",
          status: "overdue",
          content:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!",
        },
      ],
    };
  },
  methods: {
    sortBy(prop) {
      this.projects.sort((a, b) => (a[prop] < b[prop] ? -1 : 1));
    },
  },
};
</script>

<style>
.project.complete {
  border-left: 4px solid #3cd1c2;
}
.project.ongoing {
  border-left: 4px solid #ffaa2c;
}
.project.overdue {
  border-left: 4px solid #f83e70;
}
.v-chip.v-chip--no-color.theme--light.complete {
  background: #3cd1c2;
}
.v-chip.v-chip--no-color.theme--light.ongoing {
  background: #ffaa2c;
}
.v-chip.v-chip--no-color.theme--light.overdue {
  background: #f83e70;
}
</style>