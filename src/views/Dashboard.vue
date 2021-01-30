<template>
  <div class="dashboard">
    <v-container class="px-2 py-5">
      <v-row class="pb-3">
        <v-col class="ml-2" cols="6" md="2">
          <v-btn small @click="sortBy('title')">
            <v-icon small class="grey--text">mdi-folder</v-icon>
            <span class="caption text-lowercase grey--text ml-1">
              By Project Name
            </span>
          </v-btn>
        </v-col>
        <v-col class="pl-2" cols="6" md="2">
          <v-btn small @click="sortBy('person')">
            <v-icon small class="grey--text">mdi-account</v-icon>
            <span class="caption text-lowercase grey--text ml-1">
              By Person
            </span>
          </v-btn>
        </v-col>
      </v-row>
      <v-card
        v-for="project in projects"
        :key="project.title"
        class="pa-3 ma-2"
      >
        <v-row :class="`pa-3 project ${project.status}`">
          <v-col cols="12" md="6">
            <div class="grey--text">Project title</div>
            <div>{{ project.title }}</div>
          </v-col>
          <v-col cols="4" md="2">
            <div class="grey--text">Person</div>
            <div>{{ project.person }}</div>
          </v-col>
          <v-col cols="4" md="2">
            <div class="grey--text">Due By</div>
            <div>{{ project.due }}</div>
          </v-col>
          <v-col cols="4" md="2">
            <div class="text-center">
              <v-chip :class="` caption white--text my-2  ${project.status} `">
                {{ project.status }}
              </v-chip>
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Dashboard",
  components: {},

  data() {
    return {
      projects: [
        {
          title: "Design a new website",
          person: "Tanvir",
          due: "10th jan 2021",
          status: "ongoing",
        },
        {
          title: "Design web app",
          person: "Evan",
          due: "10th jan 2021",
          status: "overdue",
        },
        {
          title: "Design Ui",
          person: "Rajeeb",
          due: "6th jan 2021",
          status: "completed",
        },
        {
          title: "Develop business",
          person: "Mou",
          due: "7th jan 2021",
          status: "completed",
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
<style scoped>
.project.completed {
  border-left: 4px solid lightgreen;
}
.project.ongoing {
  border-left: 4px solid orange;
}
.project.overdue {
  border-left: 4px solid tomato;
}
.v-chip.v-chip--no-color.theme--light.completed {
  background: lightgreen;
}
.v-chip.v-chip--no-color.theme--light.ongoing {
  background: orange;
}
.v-chip.v-chip--no-color.theme--light.overdue {
  background: tomato;
}
</style>