<template>
  <div class="cravings">
    <p>Eggs 🥚:  <strong>{{ eggCount }}</strong></p>
    <hr>
    <button class="button is-primary is-outlined" @click.prevent="increment">🧸</button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      eggCount: 0,
    }
  },

  methods: {
    increment () {
      this.eggCount++
    },
  },
}
</script>
