<template>
  <div class="cravings panel">
    <div
      v-for="(craving, i) in cravings"
      :key="i"
      class="craving panel-block is-block"
    >
      <div class="level">
        <div class="level-left">
          <div class="craving-label level-item">
            {{ craving }}
          </div>
        </div>
        <div class="level-right">
          <div class="craving-actions level-item">
            <button class="button is-small is-info is-outlined" @click.prevent="remove(i)">
              <span class="icon is-small" aria-hidden="true">
                <i class="fas fa-utensils"></i>
              </span>
              <span class="action-label">Nom Nom!</span>
            </button>
          </div>
        </div>
      </div>
    </div>
    <div class="panel-block is-block">
      <div class="field has-addons">
        <div class="control is-expanded">
          <input
            v-model="newCraving"
            class="input"
            type="text"
            placeholder="What are you craving?"
            @keydown.enter.prevent="add"
          >
        </div>
        <div class="control">
          <button class="button is-primary" @click.prevent="add">
            <span class="icon" aria-hidden="true">
              <i class="fas fa-plus"></i>
            </span>
            <span class="sr-only">Add craving</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      cravings: [
        'Donuts 🍩',
        'Strawberries 🍓',
        'Croissants 🥐',
      ],
      newCraving: '',
    }
  },

  methods: {
    add () {
      if (!this.newCraving.length) return
      this.cravings.push(this.newCraving)
      this.newCraving = ''
    },

    remove (i) {
      this.cravings.splice(i, 1)
    },
  },
}
</script>
