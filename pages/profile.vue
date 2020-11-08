<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
          User Profile
        </v-card-title>
        <v-card-text>
          <p>This page is only for you.</p>
          <p>Your e-mail is {{ authUser.email }}</p>
          <v-btn @click="logout">Logout</v-btn>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import Vue from 'vue'
import { mapState, mapGetters } from 'vuex'


export default {
  layout: 'basic',
  middleware: 'auth',
  components: {
  },
  computed: {
    ...mapState(['authUser'])
  },
  methods: {
    async logout() {
      await this.$fire.auth.signOut()
      this.$router.push('/login')
    }
  }
}
</script>
