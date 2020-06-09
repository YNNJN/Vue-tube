<template>
  <div>
    <input
      class="form-control my-5"
      placeholder="동영상 검색"
      type="text"
      @keypress.enter="onInput"
      v-focus
      >
  </div>
</template>

<script>
export default {
  name: 'VideoSearch',
  methods: {
    onInput(e) {
      this.$emit('input-change', e.target.value)
    },
  },
  directives: {
    focus: {
      inserted: function (el) {
        el.focus()
      }
    }
  },
}
</script>

<style>

</style>