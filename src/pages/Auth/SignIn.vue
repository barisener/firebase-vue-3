<template>
  <div>
    <pre v-if="isAuthenticated">{{ user }}</pre>
    <div v-else>
      <q-btn
        color="primary"
        icon="mdi-google"
        :label="t('Sign in with google')"
        @click="signIn"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, watch, computed } from "vue";
import { useI18n } from "vue-i18n";
import { initializeApp } from "firebase/app";
import { GoogleAuthProvider, getAuth, signInWithPopup } from "firebase/auth";
import { useAuth } from "@vueuse/firebase/useAuth";

//#region Composables
const { t } = useI18n();
const app = initializeApp({
  apiKey: "AIzaSyC0iBfuSUVwOrAcGPzclgyXMvjjFNYxyxE",
  authDomain: "fir-vue-32053.firebaseapp.com",
  projectId: "fir-vue-32053",
  storageBucket: "fir-vue-32053.appspot.com",
  messagingSenderId: "815128910300",
  appId: "1:815128910300:web:b10d6d4aeb226ffc3c9719",
  measurementId: "G-C0X54WDT7E",
});
const auth = getAuth(app);
const { isAuthenticated, user } = useAuth(auth);
//#endregion

//#region Injects
//#endregion

//#region Props
//#endregion

//#region Emits
//#endregion

//#region Variables
//#endregion

//#region Methods
const signIn = () => signInWithPopup(auth, new GoogleAuthProvider());
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
//#endregion
</script>

<style lang="scss" scoped></style>
