<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-row>
        <v-col cols="12">
          <v-row :align="alignment" :justify="justify">
            <v-card
              v-for="n in 7"
              :key="n"
              class="ma-3 pa-6 rounded-lg neumorphism"
              tile
            >
              Column
            </v-card>
          </v-row>
          <v-row v-for="i in 5" :key="i" :align="alignment" :justify="justify">
            <v-card
              v-for="j in 7"
              :key="j"
              class="ma-3 pa-6 rounded-lg neumorphism"
              tile
            >
              Column
            </v-card>
          </v-row>
        </v-col>
        <v-col cols="12">
          <v-row justify="center">
            <v-col cols="6" md="2">
              <v-select
                v-model="alignment"
                :items="alignmentsAvailable"
                label="Align"
              ></v-select>
            </v-col>

            <v-col cols="6" md="2">
              <v-select
                v-model="justify"
                :items="justifyAvailable"
                label="Justify"
              ></v-select>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      alignmentsAvailable: ['start', 'center', 'end', 'baseline', 'stretch'],
      alignment: 'center',
      dense: false,
      justifyAvailable: [
        'start',
        'center',
        'end',
        'space-around',
        'space-between',
      ],
      justify: 'center',
    }
  },
}
</script>

<style lang="scss">
.neumorphism {
  border: none !important;
  background: #ffffea !important;
  box-shadow: 10px 10px 20px #d9d9c7, -10px -10px 20px #fffff4 !important;
}
</style>
