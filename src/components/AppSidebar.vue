<template>
  <form class="card card-w30">
    <div class="form-control">
      <app-select :id="type" :options="options"></app-select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea id="value" rows="3"></textarea>
    </div>

  </form>
</template>

<script>
import AppSelect from "@/components/AppSelect";
export default {
  name: 'AppSidebar',
  components: {AppSelect},
  data() {

    return {
      options: [
        {
          value: 'title',
          text: 'Заголовок'
        },
        {
          value: 'subtitle',
          text: 'Подзаголовок'
        },
        {
          value: 'avatar',
          text: 'Аватар'
        },
        {
          value: 'text',
          text: 'Текст'
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
