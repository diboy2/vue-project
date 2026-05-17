<script setup lang="ts">
    defineProps<{
        items: array
    }>();
</script>
<template>
  <h1>A Child Component!</h1>
  <ul class="items">
    <li v-for="item in items" :key="item.id">
      {{ item.message }}
    </li>
  </ul>

</template>