<template>
  <div class="asteroids">
    <h1>Asteroids near to Earth</h1>
    <AsteroidsList
      @select="select"
    />
    <AsteroidModal
      :asteroid="asteroid"
      @unselect="unselect"
    />
  </div>
</template>

<script>
import AsteroidsList from '@/components/asteroids/AsteroidsList'
import AsteroidModal from '@/components/asteroids/AsteroidModal'

export default {
  name: 'Asteroids',
  components: {
    AsteroidsList,
    AsteroidModal
  },
  data() {
    return {
      asteroid: null
    }
  },
  methods: {
    select(asteroid) {
      this.asteroid = asteroid
    },
    unselect() {
      this.asteroid = null
    }
  }
}
</script>
