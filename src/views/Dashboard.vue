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
<<<<<<< HEAD
  name: "Dashboard",
  components: {},

=======
>>>>>>> ee6ab29e4a4231d0b7289fe05ac99d402932325c
  data() {
    return {
      projects: [
        {
          title: "Design a new website",
<<<<<<< HEAD
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
=======
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
>>>>>>> ee6ab29e4a4231d0b7289fe05ac99d402932325c
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
<<<<<<< HEAD
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
=======

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
>>>>>>> ee6ab29e4a4231d0b7289fe05ac99d402932325c
}
</style>