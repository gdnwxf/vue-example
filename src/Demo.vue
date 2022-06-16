<template>
  <a-select
    v-model:value="value"
    label-in-value
    style="width: 120px"
    :options="options"
    @change="handleChange"
  >
  </a-select>
</template>
<script lang="ts">
import { SelectTypes } from 'ant-design-vue/es/select';
import { defineComponent, ref } from 'vue';

interface Value {
  value?: string;
  label?: string;
}

export default defineComponent({
  setup() {
    const options = ref<SelectTypes['options']>([
      {
        value: 'jack',
        label: 'Jack (100)',
      },
      {
        value: 'lucy',
        label: 'Lucy (101)',
      },
    ]);
    const handleChange = (value: Value) => {
      console.log(value); // { key: "lucy", label: "Lucy (101)" }
    };
    return {
      value: ref<Value>({ value: 'lucy' }),
      options,
      handleChange,
    };
  },
});
</script>
