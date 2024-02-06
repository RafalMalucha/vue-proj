<template>
    <div>
        <input @input="onInput" placeholder="dupaudpaudp"/>
    </div>
</template>

<script>
export default {
  name: 'SearchBar',
  methods: {
    onInput: function(event) {
        this.$emit('phraseChange', event.target.value)
    }
  }
}
</script>

<style>
</style>