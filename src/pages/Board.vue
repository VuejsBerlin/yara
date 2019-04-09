<template>
  <Layout>
    <raffle-board :members="members" />
  </Layout>
</template>

<script>
import RaffleBoard from '@/components/Board'
import CatNames from 'cat-names'
import DogNames from 'dog-names'
import Superb from 'superb'

export default {
  metaInfo: {
    title: 'YARA - Yet Another Raffle App'
  },
  components: { RaffleBoard },
  data () {
    return {
      members: [
        { verb: Superb.random(), name: CatNames.random() },
        { verb: Superb.random(), name: CatNames.random() },
        { verb: Superb.random(), name: DogNames.allRandom() },
        { verb: Superb.random(), name: DogNames.allRandom() }
      ]
    }
  }
}
</script>

<style>
</style>
