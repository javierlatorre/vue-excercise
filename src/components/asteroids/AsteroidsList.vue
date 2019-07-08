<template>
  <ul class="asteroids-list w3-ul w3-card-2">
    <Asteroid
      v-for="asteroid in asteroids"
      :key="asteroid.id"
      :asteroid="asteroid"
      @select="select"
    />
  </ul>
</template>

<script>
import nasa from '@/api/nasa'
import Asteroid from '@/components/asteroids/Asteroid'

export default {
  name: 'AsteroidsList',
  components: {
    Asteroid
  },
  data() {
    return {
      asteroids: []
    }
  },
  created() {
    this.asteroids = nasa.getAsteroids()
  },
  methods: {
    select(asteroid) {
      this.$emit("select", asteroid)
    }
  }
}
</script>

<style lang="scss">
.asteroids-list.w3-ul {
  margin: 10px;
}
</style>
