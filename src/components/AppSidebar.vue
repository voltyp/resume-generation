<template>
  <form class="card card-w30">
    <div class="form-control">
      <label for="type">Заголовок</label>

      <select id="type" v-model="selected">
        <option
            v-for="option in options"
            :value="option.value"
            :key="option.id"
        >{{ option.text }}</option>
      </select>
    </div>

    <div class="form-control">
      <label for="textarea">Значение</label>
      <textarea id="textarea" rows="3" v-model="textarea"></textarea>
    </div>

    <app-button
        color="primary"
        @click.prevent="addBlock"
        :disabled="switchDisable"

    >Добавить</app-button>
  </form>
</template>

<script>
import AppButton from "@/components/AppButton";

export default {
  name: 'AppSidebar',
  data() {

    return {
      textarea: '',
      selected: '',
      options: [
        {
          id: 1,
          value: 'title',
          text: 'Заголовок'
        },
        {
          id: 2,
          value: 'subtitle',
          text: 'Подзаголовок'
        },
        {
          id: 3,
          value: 'avatar',
          text: 'Аватар'
        },
        {
          id: 4,
          value: 'text',
          text: 'Текст'
        }
      ]
    }
  },
  created() {
    this.selected = this.options[0].value;
  },
  computed: {
    switchDisable() {
      return (this.textarea.length <= 3)
    }
  },
  methods: {
    addBlock() {
      this.$emit('add', this.selected, this.textarea);
      this.selected = this.options[0].value;
      this.textarea = '';
    }
  },
  components: {AppButton}
}
</script>

<style scoped>

</style>
