<template>
  <q-layout view="lHr lpR lFr">
    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref, watch, computed, provide } from "vue";
import { useI18n } from "vue-i18n";
//#region Composables
const { t } = useI18n();
//#endregion

//#region Injects
//#endregion

//#region Props
//#endregion

//#region Emits
//#endregion

//#region Variables
const leftDrawerOpen = ref(false);
const rightDrawerOpen = ref(false);
//#endregion

//#region Methods
//#endregion

//#region Computed Properties
//#endregion

//#region Watchers
//#endregion

//#region Lifecycle Hooks
//#endregion

//#region Created
//#endregion

//#region Providers
provide("leftDrawerOpen", leftDrawerOpen);
provide("rightDrawerOpen", rightDrawerOpen);
//#endregion
</script>

<style lang="scss" scoped></style>
