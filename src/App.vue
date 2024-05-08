<script setup lang="ts">
import { computed, ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import TeleportedView from './components/TeleportedView.vue'

const Targets = ["blue", "green"];
const Target = ref("blue");
const TargetId = computed(():string => {
  console.log(`#${Target}-target`);
  return `#${Target}-target`;
});


</script>

<template>
  <HelloWorld msg="Vue3 Teleport Lab" />

  <div style="margin-bottom:3em;">
    <label for="targets" >Select Teleport Target:</label>
    <select v-model="Target"
            style="width:120px;"
    >
      <option
        v-for="target in Targets"
        :value="target"
      >
        {{ target }}
      </option>
    </select>
  </div>
  <div id="green-target" style="color:green;border:2px dotted green;margin-bottom:3em;">GREEN</div>


  <div id="blue-target" style="color:blue;border:2px dotted blue;margin-bottom:3em;">BLUE</div>
  




<TeleportedView
  :target="`#${Target}-target`"
></TeleportedView>

</template>

<style scoped>
</style>
