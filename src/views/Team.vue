<template>
  <div class="team">
    <v-container class="px-2 py-5">
      <v-row>
        <v-col 
          cols="6"
          md="4"
          lg="4"
          v-for="teamMember in team"
          :key="teamMember.name"
        >
          <v-card link text class="pa-4 text-center">
            <v-responsive> 
              <v-avatar size="100" class=" red dakern-3">
                <img :src="teamMember.avater">
              </v-avatar>
            </v-responsive>
            <v-card-text>
              <div class="grey--text">{{ teamMember.name }}</div>

              <div class="grey--text text--darken-3">{{ teamMember.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-icon small class="grey--text">mdi-message </v-icon>
              <span class="ml-2 grey--text text--darken-3">Message</span>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      team: [
        { name: "Evan", role: "Developer", avater: "/profile.png" },
        { name: "Tanvir", role: "Website Designer", avater: "/profile.png" },
        { name: "Rajeeb", role: "Ui Designer", avater: "/profile.png" },
        { name: "Mou", role: "Business Exe", avater: "/profile1.png" },
        { name: "Asif", role: "Business Exe", avater: "/profile.png" },
      ],
    };
  },
};
</script>