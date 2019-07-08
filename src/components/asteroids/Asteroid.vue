<template>
  <li
    class="asteroid w3-bar"
    :key="asteroid.id"
  >
      <a
        href="javascript:void(0)"
        @click="select(asteroid)"
      >
        <img
          src="@/assets/asteroid.png"
          alt="Asteroid"
          class="asteroid__icon w3-bar-item"
        />
        <ul class="asteroid__properties w3-bar-item">
          <li><b>Name:</b> {{ asteroid.name }}</li>
          <li><b>Estimated diameter (km):</b> {{ asteroid.estimated_diameter.kilometers.estimated_diameter_max.toFixed(2) }}</li>
        </ul>
      </a>
    </li>
</template>

<script>
export default {
  name: 'Asteroid',
  props: {
    asteroid: {
      type: Object,
      required: true
    }
  },
  methods: {
    select(asteroid) {
      this.$emit("select", asteroid)
    }
  }
}
</script>

<style lang="scss">
.asteroid {
  text-align: left;

  &__icon {
    height: 60px;
  }

  &__properties {
    list-style: none;
    padding: 0 !important;

    li {
      padding: 0 !important;
      border-bottom: 0 !important;
    }
  }
}
</style>
