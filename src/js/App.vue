<template>
  <section class="app section">
    <div class="container">
      <div class="columns">
        <div class="column is-half-tablet is-offset-one-quarter-tablet is-one-third-desktop is-offset-one-third-desktop">
          <h1 class="title">Crave</h1>
          <cravings></cravings>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Cravings from './Cravings.vue'

export default {
  components: {
    Cravings,
  },
}
</script>
