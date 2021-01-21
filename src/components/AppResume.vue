<template>
  <div class="card card-w70">
    <p v-if="templatesIsEmpty">Добавьте первый блок, чтобы увидеть результат</p>
    <div v-else>
      <component
          v-for="template in templates"
          :is="template.name"
          :key="template.id"
          :content="template.content"
      ></component>
    </div>
  </div>
</template>

<script>
import ResumeAvatar from "@/components/resume/ResumeAvatar";
import ResumeTitle from "@/components/resume/ResumeTitle";
import ResumeSubtitle from "@/components/resume/ResumeSubtitle";
import ResumeText from "@/components/resume/ResumeText";

export default {
  name: "AppResume",
  props: {
    templates: {
      type: Array,
      required: true
    }
  },
  computed: {
    templatesIsEmpty() {
      return this.templates.length === 0;
    }
  },
  components: {ResumeAvatar, ResumeTitle, ResumeSubtitle, ResumeText}
}
</script>

