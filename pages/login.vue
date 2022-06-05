<template>
  <div>
    <TheHeader></TheHeader>
    <div>
      <form @submit.prevent="onLogin"></form>
    </div>
  </div>
</template>

<script lang="ts" setup>
import TheHeader from "../components/UI/TheHeader.vue";
import { auth } from "../plugins/firebase";

const onLogin = () => {
  console.log("login");
};
</script>
