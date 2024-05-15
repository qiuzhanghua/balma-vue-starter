<script setup lang="ts">
import { default as Button } from "@/components/Button.vue";

function onClick() {
  alert("Button clicked");
}
</script>

<template>
  <button class="button is-primary">Primary Button</button>
  <Button is-primary is-outlined class="xyz" is-large @click="onClick"
    >Primary Button</Button
  >
</template>
