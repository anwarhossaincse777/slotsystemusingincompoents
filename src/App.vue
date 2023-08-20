<script setup>

import ButtonComponent from "./components/ButtonComponent.vue";
import {ref} from "vue";
import SlotComponentsUsingSystem from "./components/SlotComponentsUsingSystem.vue";

const msg = ref("Hello World")

function clickHandlerOne() {
  msg.value = "Click Button One"
}

function clickHandlerTwo() {
  msg.value = "Click Button Number Two"
}

</script>

<template>
  <h2 class="text-2xl my-10">Slot using in  props system</h2>
  <p class="my-5">
    {{ msg }}
  </p>

  <ButtonComponent :clickHandler="clickHandlerOne" >
    <em>Button One</em>
  </ButtonComponent>

  <br>
  <br>
  <br>
  <br>

<!--  another function passing clickHandler attributes-->

  <ButtonComponent :clickHandler="clickHandlerTwo" >
    <em>Button Two</em>
  </ButtonComponent>

  <br>
  <br>
  <br>
  <br>


<!--  ..slot component with extends layout name-->


  <SlotComponentsUsingSystem>
    Default Content 123

    <template #header>
      <h2 class="text-2xl my-10">This is Heading</h2>
    </template>

    <template v-slot:footer>
      <h2 class="text-xl my-10">This is footer</h2>
    </template>

  </SlotComponentsUsingSystem>

</template>

<style scoped>

</style>
