<template>
  <h4>Balance</h4>
  <h1 id="balance">${{ total }}</h1>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

defineProps<{
  total: number;
}>();
</script>
