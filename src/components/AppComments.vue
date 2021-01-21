<template>
  <div class="container">
    <div class="card">
      <h2>Комментарии</h2>
      <ul class="list">
        <li
          class="list-item"
          v-for="comment in comments"
          :key="comment.id"
        >
          <p><strong>{{ comment.email }}</strong></p>
          <p><small>{{ comment.body }}</small></p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppComments",
  props: {
    comments: {
      type: Array
    }
  }
}

</script>
