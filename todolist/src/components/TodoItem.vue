//props中的中括号里左右需要留空白，逗号后空一格

<template>
  <li @click="handleEmit">{{content}}</li>
</template>

<script>
export default {
  props: [ 'content', 'index' ],
  methods: {
    handleEmit () {
      this.$emit('delete', this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
