<template>
  <v-app>
    <v-app-bar app>
      <v-row>
        <v-col cols="3"></v-col>

        <v-col cols="6" class="text-center">
          <v-toolbar-title class="text-h3">UNIEX</v-toolbar-title>
        </v-col>

        <v-col cols="3" class="text-right">
          <v-btn
            color="blue-grey"
            class="ma-2 white--text"
            fab
            small
            @click="loader = 'loading5'"
          >
            <v-icon dark>
              mdi-map-marker
            </v-icon>
          </v-btn>

          <v-btn
            color="blue-grey"
            class="ma-2 white--text"
            fab
            small
            @click="loader = 'loading5'"
          >
            <v-icon dark>
              mdi-magnify
            </v-icon>
          </v-btn>


          <v-menu
            v-model="login_menu"
            :close-on-content-click="false"
            :nudge-width="200"
            offset-x
          >
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                color="blue-grey"
                class="ma-2 white--text"
                fab
                small
                @click="login_menu = true"
              >
                <v-icon dark>
                  mdi-account
                </v-icon>
              </v-btn>
            </template>

            <v-card
              class="pa-4"
            >
              <v-form
                ref="form"
                v-model="valid"
                lazy-validation
              >
                <v-text-field
                  v-model="username"
                  :counter="10"
                  label="Username"
                  required
                ></v-text-field>

                <v-text-field
                  v-model="password"
                  label="Password"
                  required
                ></v-text-field>

                <v-checkbox
                  v-model="remember"
                  label="Remember me"
                  required
                ></v-checkbox>

                <v-btn
                  color="success"
                  class="mx-auto"
                  @click="login()"
                >
                  Login
                </v-btn>
              </v-form>
            </v-card>
          </v-menu>

        </v-col>
      </v-row>

      <template v-slot:extension>
        <v-tabs
          v-model="tab"
          centered
        >
          <v-tabs-slider color="primary"></v-tabs-slider>

          <v-tab
            v-for="item in items"
            :key="item"
          >
            {{ item }}
          </v-tab>
        </v-tabs>
      </template>
    </v-app-bar>

    <v-main>
      <v-tabs-items v-model="tab">
        <v-tab-item
          v-for="item in items"
          :key="item"
        >
          <v-card flat>
            <v-card-text v-text="text"></v-card-text>
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-main>

  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        login_menu: false,
        tab: null,
        items: [
          'GET QUOTES', 'FREIGHT SERVICES', 'LEARN',
        ],
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
      }
    },
  }
</script>
