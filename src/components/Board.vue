<template>
  <div class="board"> 
    
    <div class="time column"> 
      <h3>time</h3>
      
    </div>
    
    <div class="today column">
      <h3>today</h3>
      <Card v-for="card in mapColumn(`today`)" :key="card.id" v-bind:data="card"/>
      <AddCard v-bind:column="'today'" v-on:addCard="addCard"/>
    </div>
    
    <div class="tomorrow column">
      <h3>tomorrow</h3>
      <Card v-for="card in mapColumn(`tomorrow`)" :key="card.id" v-bind:data="card"/>
      <AddCard v-bind:column="'tomorrow'" v-on:addCard="addCard"/>
    </div>
    
    <div class="ubermorgen column">
      <h3>ubermorgen</h3>
      <Card v-for="card in mapColumn(`ubermorgen`)" :key="card.id" v-bind:data="card"/>
      <AddCard v-bind:column="'ubermorgen'" v-on:addCard="addCard"/>
    </div>
    
    <div class="backlog column">
      <h3>Backlog</h3>
      <Card v-for="card in mapColumn(`backlog`)" :key="card.id" v-bind:data="card"/>
      <AddCard v-bind:column="'backlog'" v-on:addCard="addCard"/>
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";
import AddCard from './AddCard'

export default {
  name: "Board",
  props: {},
  components: {
    Card, AddCard
  },
  data() {
    return {
      cards: [
      {
      id: 1,
      title: "card 1",
      duration: 30,
      column: "today",
    },
    {
      id: 2,
      title: "card 2",
      duration: 60,
      column: "today",
    },
    {
      id: 3,
      title: "card 3",
      duration: 60,
      column: "tomorrow",
    },
    {
      id: 4,
      title: "card 4",
      duration: 20,
      column: "ubermorgen",
    },
    {
      id: 5,
      title: "card 5",
      duration: 10,
      column: "today",
    },
    ]
  }
  },
  methods: {
    mapColumn(column) {
      return this.cards.filter(card => {
        return card.column === column
      })
    },
    addCard(column, input) {
      var newCard=({
        id: this.cards.length + 1,
        title: input.title,
        duration: input.duration,
        column: column
      })
      this.cards.push(newCard)
    }
  },
  
};
</script>

<style lang="scss">
.board {
  display: flex
}

</style>
