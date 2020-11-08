<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
          Main page
        </v-card-title>
        <v-card-text>
          <p>Everybody should be able to see this page even without logging in.</p>
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn
            color="primary"
            nuxt
            to="/login"
          >
            Sign In
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>

export default {
  layout: 'basic',
  components: {
  }
}
</script>
