<template>
  <div id="app">
    <hello-world parentMessage="A parent message"></hello-world>
  </div>
</template>

<script lang="coffee">
import HelloWorld from "./components/HelloWorld"

export default
  name: "App"
  data: ->
    loaded: false,
    refreshing: true,
    updateExists: false,
    registration: null
  created: () -> 
    this.func 5

  methods:
    showRefreshUI: (e) ->
      this.registration = e.detail
      this.updateExists = true

    refreshApp: ->
      this.updateExists = false
      if !this.registration || !this.registration.waiting 
        return
      this.registration.waiting.postMessage 'skipWaiting'

    func: (x) ->
      console.log "Hello " + x
  components: {
    HelloWorld
  }
</script>
