<template>
  <nav
    class="navbar navbar-main navbar-expand-lg px-0 mx-4 shadow-none border-radius-xl"
    v-bind="$attrs"
    id="navbarBlur"
    data-scroll="true"
  >
    <div class="px-3 py-1 container-fluid">
      <!-- <breadcrumbs :currentPage="currentRouteName" textWhite="text-white" /> -->
        <ul class="navbar-nav justify-content-end">
          <argon-button color="dark" variant="gradient">
            <i class="fas fa-plus me-2"></i>
            Add New Account
          </argon-button>
        </ul>
      </div>
  </nav>
</template>
<script>
// import Breadcrumbs from "./Breadcrumbs.vue";
import { mapMutations, mapActions } from "vuex";
import ArgonButton from "@/components/ArgonButton.vue";

export default {
  name: "navbar",
  data() {
    return {
      showMenu: false
    };
  },
  props: ["minNav", "textWhite"],
  created() {
    this.minNav;
  },
  methods: {
    ...mapMutations(["navbarMinimize", "toggleConfigurator"]),
    ...mapActions(["toggleSidebarColor"]),

    toggleSidebar() {
      this.toggleSidebarColor("bg-white");
      this.navbarMinimize();
    }
  },
  components: {
    // Breadcrumbs,
    ArgonButton
  },
  computed: {
    currentRouteName() {
      return this.$route.name;
    }
  }
};
</script>
