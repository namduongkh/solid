<template>
  <div>
    <Intro />
    <ul class="nav nav-pills nav-fill" role="tablist">
      <li
        class="nav-item"
        v-for="(r, index) in routes"
        :key="'route-link-' + index"
      >
        <router-link
          :to="{ name: r.name }"
          class="nav-link"
          :class="{ active: r.name == $route.name }"
          >{{ r.meta.text }}
        </router-link>
      </li>
    </ul>
    <div class="main-content">
      <div class="next-phase"></div>
      <router-view class="container"></router-view>
    </div>
  </div>
</template>

<script>
import routes from "../config/routes";
import Intro from "./Intro.vue";

export default {
  name: "App",
  data() {
    return {
      routes,
    };
  },
  components: {
    Intro,
  },
};
</script>

<style>
</style>
