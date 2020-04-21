<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
  </div>
</template>

<script>
import vHeader from './components/v-header/v-header'
import { getSeller } from './api'

export default {
  name: 'App',
  data() {
    return {
      seller: {}
    }
  },
  created() {
    this._getSeller()
  },
  methods: {
    _getSeller() {
      getSeller().then(res => {
        this.seller = res
      })
    }
  },
  components: {
    vHeader
  }
}
</script>

<style lang="stylus"></style>
