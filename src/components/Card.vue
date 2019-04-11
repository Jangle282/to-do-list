<template>
    <div class="card">
      <h3>{{data.title || "Hello!"}}</h3>
      <p>{{data.duration}}</p>
    </div>
</template>

<script>
export default {
name: "Card",
  props: ['data']
}
</script>

<style lang="scss">
.card {
    background-color: red;
    height: 100px;
    width: 200px;  
    border: 1px solid black
}
</style>
