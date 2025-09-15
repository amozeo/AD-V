<script>
import preinfinityupgradebutton from "./preinfinityupgrade";

export default {
  name: "Glitchreality",
  components: {
    preinfinityupgradebutton
  },
  computed: {
    upgrades: () => realityUGs.all
  },
  methods: {
    id(row, column) {
      return (row - 1) * 7 + column - 1;
    }
  }
};
</script>

<template>
  <div class="l-reality-upgrade-grid">
    <div class="c-reality-infotext">
      Here we are
      <br>
      The end is nigh
      <br>
      the most powerful
    </div>

    <div
      v-for="row in 2"
      :key="row"
      class="l-reality-upgrade-grid__row"
    >
      <preinfinityupgradebutton
        v-for="column in 7"
        :key="id(row, column)"
        :upgrade="upgrades[id(row, column)]"
      />
    </div>
  </div>
</template>

<style scoped>
.c-reality-infotext {
  color: var(--color-text);
  margin: 1.5rem 0 1.5rem;
}
</style>
