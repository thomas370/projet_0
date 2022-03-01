<template>
<v-container class="spacing-playground pa-6"
    fluid>
  <v-row align="center" justify="space-around">
    <v-btn color="primary" v-on:click="(code = Math.floor(Math.random() * (25 - 1 + 1)) + 1 ) + (erreur= Math.floor(Math.random() * (5 - 1 + 1)) + 1 )">Coder-bien </v-btn>
    <v-btn  color="primary" v-on:click="(code = Math.floor(Math.random() * (30 - 1 + 1)) + 1 ) + (erreur= Math.floor(Math.random() * (70 - 1 + 1)) + 1 )">Coder-vite</v-btn>
    <v-btn  color="primary" v-on:click="(code+=erreur)+(erreur = 0)">tester</v-btn>
    <v-btn  color="primary" v-on:click="(code = 0)+( erreur = 0 )">Abandonner</v-btn>
  </v-row>
  <br>
 <v-progress-linear
      v-model="erreur"
      color="orange"
      height="25"
    >
      <template v-slot:default="{ value }">
        <strong>{{ Math.ceil(value) }}%  erreurs</strong>
      </template>
    </v-progress-linear>
    <br>
    <v-progress-linear
      v-model="code"
      color="blue"
      height="25"
    >
      <template v-slot:default="{ value }">
        <strong>{{ Math.ceil(value) }}%  codes</strong>
      </template>
    </v-progress-linear>
</v-container>
</template>

<script>
export default {
  data: () => ({
    erreur: 20,
    code: 33
  })
}
</script>
