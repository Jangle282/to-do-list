<template>
  <div class="card">
    <button @click="toggleAddForm">Add Card</button>
    <form v-if="this.form">
      <input type="text" v-model="newCard.title">
      <input type="number" v-model="newCard.duration">
    </form>
    <button v-on:click="$emit('addCard', column, newCard)">Add a card{{column}}</button>
  </div>
</template>

<script>
export default {
name: "AddCard",
props: ['column'],
data() {
    return {
      form: false,
        newCard: {
          title: "",
          duration: 0,
        }
    }
  },
  methods: {
    toggleAddForm() {
      this.form = !this.form
    }

  }
}


</script>

<style lang="scss">

</style>
