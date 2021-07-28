<template>
  <div>
    <normal-input />
    <custom-input
      v-model:searchWord="searchText"
      validator-prop="success"
    />
    <model-value-input
      v-model="sampleText"
      validator-prop="danger"
    />
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue';
import NormalInput from './components/Input.vue';
import CustomInput from './components/CustomInput.vue';
import ModelValueInput from './components/ModelValueInput.vue';

export default defineComponent({
  name: 'App',
  components: {
    NormalInput,
    CustomInput,
    ModelValueInput,
  },
  setup() {
    const searchText = ref('aaa');
    const sampleText = ref('bbb');
    return {
      searchText,
      sampleText,
    }
  }
})
</script>

<style>
</style>
