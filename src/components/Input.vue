<template>
  <div>
    <p>{{ searchText }}</p>
    <input v-model="searchText">
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'Input',
  setup() {
    const searchText = ref();
    return {
      searchText,
    }
  }
})
</script>

<style>

</style>
