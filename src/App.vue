<template>
  <div class="container column">
    <app-sidebar @add="getTemplate"></app-sidebar>
    <app-resume :templates="templates"></app-resume>
  </div>
  <div class="container">
    <app-button v-if="loadComments" color="primary mb-1" @click="getComments">Загрузить комментарии</app-button>
    <app-loader v-if="commentsLoader"></app-loader>
    <AppComments v-else-if="!loadComments" :comments="comments"></AppComments>
  </div>
</template>

<script>
import AppSidebar from "@/components/AppSidebar";
import AppComments from "@/components/AppComments";
import AppButton from "@/components/AppButton";
import AppResume from "@/components/AppResume";
import AppLoader from "@/components/AppLoader"

export default {
  data() {

    return {
      templates: [],
      comments: [],
      commentsUrl: 'https://jsonplaceholder.typicode.com/comments?_limit=42',
      loadComments: true,
      commentsLoader: false
    }
  },
  methods: {
    getTemplate(name, content) {
      this.templates.push({
        id: this.templates.length + 1,
        name: 'resume-' + name,
        content
      })
    },
    async getComments() {
      this.loadComments = false;
      this.commentsLoader = true;
      const param = {
        methods: 'GET',
        headers: {
          'Content-Type': 'application/json'
        }
      };
      const comments = await fetch(this.commentsUrl, param);
      this.comments = await comments.json();
      this.commentsLoader = false;
    }
  },
  components: {
    AppSidebar,
    AppResume,
    AppComments,
    AppButton,
    AppLoader
  }
}
</script>
