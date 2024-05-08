<script setup lang="ts">
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import TeleportedView from './components/TeleportedView.vue'

const Targets = ["blue", "green"];
const Target = ref(Targets[0]);

</script>

<template>
<!-- Beginning of main app component tree -->
  <div>
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

<!-- Targets -->
  <div id="blue-target" style="color:blue;border:2px dotted blue;margin-bottom:3em;">BLUE</div>
  <div id="green-target" style="color:green;border:2px dotted green;margin-bottom:3em;">GREEN</div>

</div><!-- End of main app component tree -->


<!-- Note this is OUTSIDE of the main app component tree, otherwise it would not render. -->
<TeleportedView
  :target="`#${Target}-target`"
/>

</template>
