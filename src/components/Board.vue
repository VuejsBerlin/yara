<template>
  <div id="board">
    <ol>
      <li v-for="member in members">
        <Ticket :key="member.id" v-bind="member" />
      </li>
    </ol>
  </div>
</template>

<script>
import Ticket from '@/components/Ticket'

export default {
  props: {
    members: Array
  },
  components: { Ticket }
}
</script>

<style scoped>
#board > ol {
  list-style-type: none;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  margin: 0;
  padding: 0;
}
#board > ol > li {
  background: black;
  width: 15em;
  text-align: center;
  margin: .6em 0;
}
</style>
