<script>
import axios from "axios";

export default {
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
  beforeMount() {},
  mounted() {
    this.fetchProject();
  },
}
</script>

<template>
  <div>
    <h1>funziona?</h1>
</div>
</template>

<style lang="scss">@use "styles/main";</style>