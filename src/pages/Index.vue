<template>
  <Layout>
    <generator v-model="result" />
  </Layout>
</template>

<script>
import Generator from '@/components/Generator'

export default {
  name: 'IndexPage',
  metaInfo: {
    title: 'YARA - Yet Another Raffle App'
  },
  components: { Generator },
  data () {
    return {
      result: {
        verb: '',
        name: ''
      }
    }
  }
}
</script>

<style>
.sa, .sa-success, .sa-error,
.sa-success::before, .sa-error::before,
.sa-success::after, .sa-error::after,
.sa-success-fix, .sa-error-fix {
  background-color: black !important;
}
</style>
