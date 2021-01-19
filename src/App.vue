<template>
  <div class="container column">
    <app-sidebar></app-sidebar>
    <app-information></app-information>
  </div>
  <app-button class="primary mb-1">Загрузить комментарии</app-button>
  <AppComments></AppComments>
</template>

<script>
import AppSidebar from "@/components/AppSidebar";
import AppInformation from "@/components/AppInformation";
import AppComments from "@/components/AppComments";
import AppButton from "@/components/AppButton";

export default {
  data() {

    return {

    }
  },
  components: {
    AppSidebar,
    AppInformation,
    AppComments,
    AppButton
  }
}
</script>

<style>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>
