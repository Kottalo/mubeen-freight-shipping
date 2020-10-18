<template>
  <v-row justify="center">
    <v-dialog
      v-model="dialog"
      persistent
      width="700px"
    >
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="success"
          text
          dark
          v-bind="attrs"
          v-on="on"
        >
          Sign Up
        </v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="headline mx-auto text-h4">Sign Up</span>
        </v-card-title>

        <v-card-text>
          <v-container>
            <v-row>
              <span class="text-h5">User details</span>
            </v-row>

            <v-row>
              <v-autocomplete
                solo
                dense
                label="SELECT LOCATION"
              >
              </v-autocomplete>
            </v-row>
            <v-row>
              <v-col cols="2" class="pl-0 pr-2">
                <v-select
                  solo
                  dense
                  label="GENDER"
                >
                </v-select>
              </v-col>
              <v-col cols="5" class="pl-0 pr-0">
                <v-text-field
                  solo
                  dense
                  label="FIRST NAME"
                >
                </v-text-field>
              </v-col>
              <v-col cols="5" class="pl-2 pr-0">
                <v-text-field
                  solo
                  dense
                  label="LAST NAME"
                >
                </v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-text-field
                solo
                dense
                label="COMPANY NAME"
              >
              </v-text-field>
            </v-row>
            <v-row>
              <v-col cols="2" class="pl-0 pr-2">
                <v-select
                  solo
                  dense
                  label="MOBILE"
                >
                </v-select>
              </v-col>
              <v-col cols="5" class="pl-0 pr-0">
                <v-text-field
                  solo
                  dense
                  label="CODE"
                >
                </v-text-field>
              </v-col>
              <v-col cols="5" class="pl-2 pr-0">
                <v-text-field
                  solo
                  dense
                  label="PHONE"
                >
                </v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-text-field
                solo
                dense
                label="COMPANY NAME"
              >
              </v-text-field>
            </v-row>

            <v-divider></v-divider>

            <v-row>
              <span class="text-h5">Login details</span>
            </v-row>

            <v-row>
              <v-text-field
                solo
                dense
                label="EMAIL"
              >
              </v-text-field>
            </v-row>

            <v-row>
              <v-col cols="6" class="pl-0 pr-1">
                <v-text-field
                  solo
                  dense
                  label="PASSWORD"
                  type="password"
                >
                </v-text-field>
              </v-col>
              <v-col cols="6" class="pl-1 pr-0">
                <v-text-field
                  solo
                  dense
                  label="CONFIRM PASSWORD"
                  type="password"
                >
                </v-text-field>
              </v-col>
            </v-row>
          </v-container>
        </v-card-text>

        <v-card-actions class="mx-12">
          <v-row>
            <v-col cols="4" offset="2">
              <v-btn
                color="secondary"
                block
                @click="dialog = false"
              >
                Cancel
              </v-btn>
            </v-col>
            <v-col cols="4">
              <v-btn
                color="success"
                block
                @click="dialog = false"
              >
                Sign Up
              </v-btn>
            </v-col>
          </v-row>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
  export default {
    data: () => ({
      dialog: false,
    }),
  }
</script>

<style>
  .v-text-field__details
  {
    display: none
  }
</style>
