<template>
  <div class="container">

    <app-loader v-if="false"></app-loader>
    <div class="card">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item">
          <div>
            <p><strong>test@microsoft.com</strong></p>
            <small>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi, reiciendis.</small>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import AppLoader from '@/components/AppLoader'

export default {
  name: "AppComments",
  components: {AppLoader}
}

</script>

<style scoped>

</style>
