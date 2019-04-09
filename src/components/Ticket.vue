<template>
  <div class="ticket">
    <h2>{{ verb }}</h2>
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
export default {
  props: {
    verb: String,
    name: String
  }
}
</script>

<style scoped>
.ticket {
  padding: 2em 0;
  font-size: 1.2em;
}
.ticket > h1,
.ticket > h2 {
  margin: 0;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nobreak;
}
</style>
