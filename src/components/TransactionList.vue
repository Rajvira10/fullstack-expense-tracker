<template>
  <h3>History</h3>
  <ul id="list" class="list">
    <li
      v-for="transaction in transactions"
      :key="transaction.id"
      :class="transaction.amount < 0 ? 'minus' : 'plus'"
    >
      {{ transaction.text }} <span>$ {{ transaction.amount }}</span
      ><button class="delete-btn" @click="deleteTransaction(transaction.id)">
        x
      </button>
    </li>
  </ul>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

interface Transaction {
  id: number;
  text: string;
  amount: number;
}

defineProps<{
  transactions: Transaction[];
}>();

const emit = defineEmits(["deleteTransaction"]);

const deleteTransaction = (id: number) => {
  emit("deleteTransaction", id);
};
</script>
