<template>
  <div>
    <h1>Board</h1>
    <Board/>
  </div>
</template>

<script>
// @ is an alias to /src
import Board from "@/components/Board.vue";

export default {
  name: "home",
  components: {
    Board
  }
};
</script>
