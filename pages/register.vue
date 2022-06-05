<template>
  <h1>Create an Account</h1>
  <form @submit.prevent="onRegister">
    <div>
      <input type="text" placeholder="Email" v-model="email" />
    </div>
    <div>
      <input type="password" placeholder="Password" v-model="password" />
    </div>
    <button type="button" @click="signInWithGoogle">Sign in with Google</button>
  </form>
</template>

<script lang="ts" setup>
import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";

const router = useRouter();

const email = ref("");
const password = ref("");
const onRegister = () => {
  createUserWithEmailAndPassword(getAuth(), email.value, password.value)
    .then((data) => {
      console.log("Success");
      console.log(data);
      navigateTo({
        path: "/main",
      });
    })
    .catch((error) => {
      console.log(error);
      alert(error.message);
    });
};

const signInWithGoogle = () => {};
</script>
