<!--
=========================================================
* Vue Argon Dashboard 2 - v3.0.0
=========================================================

* Product Page: https://creative-tim.com/product/vue-argon-dashboard
* Copyright 2022 Creative Tim (https://www.creative-tim.com)

Coded by www.creative-tim.com

=========================================================

* The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
-->
<template>
    <navbar
    />
  </template>
  <script>
  
  import Navbar from "@/components/Navbar.vue";
  import { mapMutations } from "vuex";
  
  export default {
    name: "App",
    components: {
        ArgonButton
    },
    methods: {
      ...mapMutations(["toggleConfigurator", "navbarMinimize"])
    },
    computed: {
      navClasses() {
        return {
          "position-sticky bg-white left-auto top-2 z-index-sticky":
            this.$store.state.isNavFixed && !this.$store.state.darkMode,
          "position-sticky bg-default left-auto top-2 z-index-sticky":
            this.$store.state.isNavFixed && this.$store.state.darkMode,
          "position-absolute px-4 mx-0 w-100 z-index-2": this.$store.state
            .isAbsolute,
          "px-0 mx-4": !this.$store.state.isAbsolute
        };
      }
    },
    beforeMount() {
      this.$store.state.isTransparent = "bg-transparent";
    }
  };
  </script>  