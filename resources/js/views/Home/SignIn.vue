<template>
  <div class="text-center">
    <v-menu
      v-model="menu"
      :close-on-content-click="false"
      offset-x
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          fab
          x-large
          color="success"
          dark
          v-bind="attrs"
          v-on="on"
          class="ma-0"
        >
          <v-icon>mdi-account</v-icon>
        </v-btn>
      </template>

      <v-card color="blue-grey lighten-5">
        <v-card-title>
          <span class="mx-auto">
            Sign In
          </span>
        </v-card-title>

        <v-card-text class="mx-8" style="width: 300px">
          <v-form
            ref="form"
            v-model="valid"
            lazy-validation
          >
            <v-text-field
              solo
              v-model="name"
              :counter="10"
              :rules="nameRules"
              label="Username"
              required
            ></v-text-field>

            <v-text-field
              solo
              v-model="email"
              :rules="emailRules"
              label="Password"
              type="password"
              required
            ></v-text-field>
          </v-form>

          <SignUp></SignUp>
        </v-card-text>

        <v-card-actions>
          <v-btn
            color="primary"
            @click="menu = false"
            class="mx-auto"
          >
            Sign In
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-menu>
  </div>
</template>

<script>
  import SignUp from './SignUp'

  export default {
    components: {
      SignUp,
    },
    data: () => ({
      fav: true,
      menu: false,
      message: false,
      hints: true,

      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Username is required',
        v => (v && v.length <= 16) || 'Username must be less than 16 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'Password is required',
      ],
    }),

    methods: {
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      },
    },
  }
</script>
