<script>
import ProjectCards from "./components/ProjectCards.vue"
import TheHeader from "./components/TheHeader.vue"

import axios from "axios";

export default {
  components: {ProjectCards,TheHeader},
  data() {
    return {
      mioUrl: "http://localhost:8000",
      project: [],
    };
  },
  methods: {
    fetchProject() {
      axios.get(this.mioUrl + "/api/projects").then((resp) => {
        this.project = resp.data;
      });
    },
  },
  beforeMount() { },
  mounted() {
    this.fetchProject();
  },
}
</script>

<template>
  <div class="container">
    <div>
      <TheHeader></TheHeader>
    </div>
    <div>
      <ProjectCards></ProjectCards>
    </div>
    <div>
      <router-view></router-view>
    </div>
</div>
</template>

<style lang="scss">

@use "styles/main";

</style>