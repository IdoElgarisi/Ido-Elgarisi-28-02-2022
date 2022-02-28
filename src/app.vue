<template>
  <div class="app">
    <app-header />
    <router-view />
  </div>
</template>

<script>
import appHeader from "@/cmps/app-header.vue";

export default {
  name: "root-cmp",
  data() {
    return {
      initialData: { Key: "215854", LocalizedName: "Tel Aviv" },
    };
  },
  async created() {
    this.loadInitialCity(this.initialData);
  },
  computed: {

  },
  methods: {
    loadInitialCity(city) {
      this.$store.dispatch({ type: "loadCurrCity", city });
    },
  },
  components: {
    appHeader,
  },
};
</script>
