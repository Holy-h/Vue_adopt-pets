<template>
    <div>
        <h1>Pet Detail View</h1>
        <h3>{{ animal.name }} ({{ $route.params.species }})</h3>
        <p>나이: {{ animal.age }}살</p>
        <p>종: {{ animal.breed }}</p>
    </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  methods: {
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.animal = animal
  }
}
</script>
