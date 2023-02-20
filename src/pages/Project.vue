
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
  beforeMount() { },
  mounted() {
    this.fetchProject();
  },
}
</script>




<template>
  <section class="">
    <div class="text-center text-primary pt-4">
      <h1>Lista prgetti</h1>
    </div>
    <div class="">
      <div class="container py-5">
        <div class="row g-4">
          <div class="col-3" v-for="project in project" :key="project.id">
            <div class="card text-center bg-success h-100">
              <img :src="project.cover_img" class="card-img-top" alt="...">
              <div class="card-body p-0 py-3">
                <h3 class="card-title">{{ project.name }}</h3>
                <h5>Descrizione: {{ project.description }}</h5>
                <h5>GitHub Link: {{ project.github_link }}</h5>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>




<style scoped></style>