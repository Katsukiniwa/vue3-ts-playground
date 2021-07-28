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

<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue';
import axios from 'axios';
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
    if (process.env.NODE_ENV === 'development') {
      const { worker } = require('./mocks/browser');
      worker.start();
    }
    
    const searchText = ref<string>('aaa');
    const sampleText = ref('bbb');
    const getData = async () => {
      const response = await axios.get('/novels');
      console.dir(response.data)
      return response
    }
    onMounted(getData);
    return {
      searchText,
      sampleText,
    }
  }
})
</script>

<style>
</style>
