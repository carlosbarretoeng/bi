<template>
  <q-layout view="hHh Lpr lFr">
    <q-header>
      <q-toolbar>
        <q-btn flat round icon="fas fa-bars" />

        <q-toolbar-title class="text-h4 text-weight-bolder text-center">
          AGOSTINI
        </q-toolbar-title>

        <q-btn flat round icon="fas fa-bars" />
      </q-toolbar>
    </q-header>

    <q-footer>
      <q-tabs
        v-model="tabs"
        switch-indicator
        indicator-color="white"
      >
        <q-tab name="mails" icon="mail" label="Contas" />
        <q-tab name="alarms" icon="alarm" label="Extrato" />
        <q-tab name="movies" icon="movie" label="Preços" />
      </q-tabs>
    </q-footer>

    <q-drawer
      show-if-above
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>
      </q-list>
    </q-drawer>

    <q-page-container class="bg-primary">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tabs = ref(null);
</script>
