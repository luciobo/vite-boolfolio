<script>
import ProjectCards from "./components/ProjectCards.vue"
import axios from "axios";

export default {
  components: {ProjectCards},
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
    <h1>funziona?</h1>
    <div>
      <ProjectCards></ProjectCards>
    </div>
</div>
</template>

<style lang="scss">@use "styles/main";</style>