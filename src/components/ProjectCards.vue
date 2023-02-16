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
   <h1>ciao ciao</h1>
   <section class="bg-green">
      <div class="text-center text-primary pt-4">
         <h1>Lista prgetti</h1>
      </div>
      <div class="">
         <div class="container py-5">
            <div class="row g-4">

               <div class="col-3">
                  <div class="card text-center bg-success">
                     <img src="{{  }}" class="card-img-top" alt="...">
                     <div class="card-body p-0 py-3">
                        <h3 class="card-title">{{ }}</h3>
                        <h5>Descrizione: {{ }}</h5>
                        <h5>GitHub Link: {{ }}</h5>
                     </div>
                  </div>
               </div>

            </div>
         </div>
      </div>
   </section>
</template>




<style scoped></style>