<script>
import { RouterLink, RouterView } from 'vue-router'

export default {
  data() {
    return {
      path: this.$route.path,
    }
  },
  mounted() {
    console.log(this.path)
  },

}
</script>

<template>
  <div class="container-fluid">
    <div class="row flex-nowrap">
      <div class="col-auto col-md-3 nopadding col-xl-2 bg-dark min-vh-100">
        <ul class="nav flex-column bg-color fw-bold">
          <li class="nav-item fw-bold fs-1 p-3 m-auto text-white">GPP</li>
          <li class="nav-item">
            <RouterLink class="nav-link text-white py-3" aria-current="page" to="/">
              <i class="fa-solid fa-chart-line me-2"></i>Home
            </RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink
              class="nav-link text-white py-3"
              aria-current="page"
              to="/profitability"
            >
              <i class="fa-solid fa-rocket me-2"></i>Profitability Report
            </RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink
              class="nav-link text-white py-3"
              aria-current="page"
              to="/project-cost"
            >
              <i class="fa-solid fa-briefcase me-2"></i>Project Cost Report
            </RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink
              class="nav-link text-white py-3"
              aria-current="page"
              :class="{ active: this.$route.path.indexOf(`logtime`) !== -1 }"
              to="/logtime"
            >
              <i class="fa-solid fa-business-time me-2"></i>Logtime Report
            </RouterLink>
          </li>
        </ul>
      </div>

      <div class="col-10">
        <RouterView />
      </div>
    </div>
  </div>
</template>

<style>
.bg-color a:hover {
  background-color: white;
  color: black !important;
}
.nopadding {
  padding: 0 !important;
}

a.active {
  background-color: white;
  color: black !important;
}
</style>
