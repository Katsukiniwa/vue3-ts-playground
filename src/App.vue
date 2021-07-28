<template>
  <div>
    <normal-input />
    <custom-input v-model="searchText" validator-prop="succes" />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
import NormalInput from './components/Input.vue';
import CustomInput from './components/CustomInput.vue';

export default defineComponent({
  name: 'App',
  components: {
    NormalInput,
    CustomInput,
  },
  setup() {
    const searchText = ref('');
    return {
      searchText,
    }
  }
})
</script>

<style>
</style>
