<template>
  <div>
    <p>normal input</p>
    <p>{{ searchText }}</p>
    <!-- <input v-model="searchText"> -->
    <input :value="searchText" @input="searchText = $event.target.value">
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'NormalInput',
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
