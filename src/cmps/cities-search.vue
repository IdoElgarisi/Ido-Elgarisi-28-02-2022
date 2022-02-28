<template>
  <div class="search-box-wrapper flex column">
    <section class="search-box-container flex justify-center align-center">
      <section class="search-box">
        <input
          type="text"
          v-model="searchTxt"
          @input="onSearch"
          placeholder="City"
          ref="elSearch"
        />
      </section>
    </section>
    <section class="results-container" v-if="this.searchTxt">
      <ul class="search-results-list">
        <li
          v-for="place in places"
          :key="place.LocalizedName"
          :place="place"
          @click="onSelectPlace(place)"
        >
          <div class="city-list-item">
            <p>
              {{ `${place.LocalizedName}, ${place.Country.LocalizedName}` }}
            </p>
          </div>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  name: "cities-search",
  props: ["places"],
  data() {
    return {
      searchTxt: "",
    };
  },
  mounted() {
    const { elSearch } = this.$refs;
    elSearch.focus();
  },
  methods: {
    async onSearch() {
      this.$emit("setPlacesSearch", this.searchTxt);
    },
    onSelectPlace(place) {
      this.$emit("selectCity", place);
      this.searchTxt = "";
    },
  },
  computed: {},
  watch: {},
};
</script>
