<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
          Sign In
        </v-card-title>
        <v-card-text>
          <p>We only accept social auth here:</p>
          <v-btn @click="signInWithGoogle" color="primary" class="ma-2">Sign in with Google</v-btn>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>

export default {
  layout: 'basic',
  components: {
  },
  methods: {
    async signInWithGoogle() {
        var provider = new this.$fireModule.auth.GoogleAuthProvider();
       // You can add or remove more scopes here provider.addScope('https://www.googleapis.com/auth/contacts.readonly');
        let authData = await this.$fire.auth.signInWithPopup(provider)
        this.$router.push('/profile')
    }
  }
}
</script>
