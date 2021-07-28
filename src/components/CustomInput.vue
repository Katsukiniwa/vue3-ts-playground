<template>
  <div>
    <p>custom input</p>
    <input
      v-bind:value="searchWord"
      v-on:input="$emit('update:searchWord', $event.target.value)"
    >
    <span>{{ searchWord }}</span>
  </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CustomInput',
  props: {
    searchWord: {
      type: String,
      required: true
    },
    validatorProp: {
      type: String,
      required: true,
      validator: function (value) {
        // プロパティの値は、必ずいずれかの文字列でなければならない
        return ['success', 'warning', 'danger'].indexOf(value) !== -1
      }
    }
  },
  setup() {
  }
})
</script>

<style>

</style>
