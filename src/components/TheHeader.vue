<script>
export default {
  data() {
    return {
      menuItems: [
        {
          label: "Home",
          routeName: "home",
        },
        {
          label: "Project",
          routeName: "projects.index",
        },
        {
          label: "Chi Siamo",
          routeName: "about",
        },
        {
          label: "Contatti",
          routeName: "contacts",
        },
      ],
    };
  },
};
</script>

<template>
  <section>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown"
            aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNavDropdown">
          <ul class="navbar-nav">
            <li class="nav-item" v-for="(item, index) in menuItems" :key="index">
              <router-link to="{ name: item.routeName }">
                {{ item.label }}
              </router-link>
              <a class="nav-link active" aria-current="page" href="#">{{ item.label }}</a>
            </li>
            <li class="nav-item dropdown">
              <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown"
                  aria-expanded="false">
                Dropdown link
              </a>
              <ul class="dropdown-menu">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><a class="dropdown-item" href="#">Something else here</a></li>
              </ul>
            </li>
          </ul>
        </div>
      </div>
    </nav>
</section>
</template>

<style scoped lang="scss"></style>