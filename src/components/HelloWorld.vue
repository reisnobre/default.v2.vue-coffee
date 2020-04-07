<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>{{ parentMessage }}</h2>
  </div>
</template>

<script lang="coffee">
export default
  name: "HelloWorld"
  props:
    parentMessage:
      default: 'none'
  data: -> msg: 'Test'
</script>
