<template>
  <div class="py-4 container-fluid">
    <div class="row">
      <nav aria-label="breadcrumb">
        <h6 class="mb-0 font-weight-bolder">Jurnal Bank Feeds</h6>
      </nav>
    </div>
    <div class="col mb-3 justify-content-end text-right">
          <argon-button color="dark" variant="gradient">
            <i class="fas fa-plus me-2"></i>
            Add New Account
          </argon-button>
    </div>
    <div class=" row">
        <authors-table />
    </div>
  </div>
</template>

<script>
import AuthorsTable from "../components/AuthorsTable.vue";
import Navbar from "@/components/Navbar.vue";

export default {
  name: "tables",
  components: {
    AuthorsTable,
    Navbar
  },
  data() {
    return {
      stats: {
        titleColor: "opacity-7 text-white",
        descColor: "text-white",
        trip: {
          title: "Today's Trip",
          desc: "145 KM",
          classIcon: "text-dark ni ni-money-coins",
        },
        health: {
          title: "Battery Health",
          desc: "99 %",
          classIcon: "text-dark ni ni-controller ",
        },
        speed: {
          title: "Average Speed",
          desc: "56 Km/h",
          classIcon: "text-dark ni ni-delivery-fast",
        },
        volume: {
          title: "Music Volume",
          desc: "15/100",
          classIcon: "text-dark ni ni-note-03",
        },
      },
    };
  },
};
</script>
