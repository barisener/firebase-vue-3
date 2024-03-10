<template>
  <div>
    <pre>{{ user }}</pre>
    <pre>{{ isAuthenticated }}</pre>
    <div>
      <q-btn
        color="primary"
        icon="mdi-google"
        :label="t('Sign in with google')"
        @click="signIn"
      />
      <q-btn
        color="primary"
        icon="mdi-logout"
        :label="t('Sign out')"
        @click="signOut()"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, watch, computed } from "vue";
import { useI18n } from "vue-i18n";
import { initializeApp } from "firebase/app";
import {
  GoogleAuthProvider,
  getAuth,
  signInWithPopup,
  signOut as signOutFromFirebase,
} from "firebase/auth";
import { useAuth } from "@vueuse/firebase/useAuth";

//#region Composables
const { t } = useI18n();
const app = initializeApp({
  apiKey: process.env.FIREBASE_API_KEY,
  authDomain: "fir-vue-32053.firebaseapp.com",
  projectId: "fir-vue-32053",
  storageBucket: "fir-vue-32053.appspot.com",
  messagingSenderId: "815128910300",
  appId: process.env.FIREBASE_APP_ID,
  measurementId: process.env.FIREBASE_MEASUREMENT_ID,
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
const signOut = () => {
  signOutFromFirebase(auth)
    .then(() => {
      console.log("Sign out successful");
    })
    .catch((error) => {
      console.log("Sign out error", error);
    });
};
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
