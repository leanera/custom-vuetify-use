<template>
  <v-container>
    <v-row justify="center">
      <img alt="Vue logo" src="../assets/logo.png" />
    </v-row>
    <v-row justify="center">
      <lea-login-form />
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class LoginPage extends Vue {}
</script>
