<template>
  <label :for="id">Тип блока</label>
  <select :id="id">
    <option
        v-for="option in options"
        :value="option.value"
        :key="option.id"
    >{{ option.text }}</option>
  </select>
</template>

<script>
export default {
  name: 'AppSelect',
  props: {
    id: {
      type: [Number, String],
      required: true
    },
    options: Array
  }
}
</script>
