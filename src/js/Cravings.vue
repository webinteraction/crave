<template>
  <div class="cravings panel">
    <div
      v-for="(craving, i) in cravings"
      :key="i"
      :class="{
        'craving': true,
        'panel-block': true,
        'is-block': true,
        'shrinky-dink': shrinkingIndex === i,
      }"
      @animationend="remove(i)"
    >
      <div class="level">
        <div class="level-left">
          <div class="craving-label level-item">
            {{ craving }}
          </div>
        </div>
        <div class="level-right">
          <div class="craving-actions level-item">
            <button
              class="button is-small is-info is-outlined"
              @click.prevent="shrink(i)"
            >
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
      shrinkingIndex: undefined,
    }
  },

  methods: {
    add () {
      if (!this.newCraving.length) return
      this.cravings.push(this.newCraving)
      this.newCraving = ''
    },

    remove (i) {
      if (this.shrinkingIndex !== i) return
      this.cravings.splice(i, 1)
      this.shrinkingIndex = undefined
    },

    shrink (i) {
      this.shrinkingIndex = i
    },
  },
}
</script>
