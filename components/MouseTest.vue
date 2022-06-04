<template>
  <div>pos: {{ x }}, {{ y }}</div>
</template>

<script setup lang="ts">
const { x, y } = useMouse();
</script>
