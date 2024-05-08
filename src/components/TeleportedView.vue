<script setup lang="ts">
const props = defineProps({
  target: { type: String, default: "This is my default value!" },
})
</script>
<template>
  <Teleport :to="props.target">
    <div>Howdy from a teleported `.vue` file</div>
  </Teleport>
</template>