<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title> Quasar Notas </q-toolbar-title>
        <div v-if="!!route.meta.backButton">
          <q-btn icon="arrow_back" flat @click="router.go(-1)" />
        </div>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>
<script>
import { useRoute, useRouter } from "vue-router";
export default {
  name: "MainLayout",
  setup() {
    const route = useRoute();
    const router = useRouter();

    return {
      route,
      router
    };
  },
};
</script>
