<template>
  <div>
    <!-- PART 1: Pass in a "complete" prop here -->
    <Instructions complete="true" />
    <!-- PART 4: Modify the Show component to accept all of these props -->
    <div>
      <h5>Add Show</h5>
      <input v-model="name" type="text" placeholder="Name"/>
      <button v-on:click="addShow(name)">Add Show</button>
    </div>
    <Show
      v-for="show in shows"
      :key="show.id"
      :id="show.id"
      :name="show.name"
      :episodes_seen="show.episodes_seen"
    />
  </div>
</template>

<script>
import Instructions from "./Instructions.vue";
import Show from "./Show.vue";

export default {
  components: {
    Instructions,
    Show
  },
  methods: {
    addShow: function(namearg){
      this.shows.push({id:this.shows.length+1, name:namearg, episodes_seen:0})
  }},
  data() {
    return {
      shows: [
        { id: 1, name: "Game of Thrones", episodes_seen: 0 },
        { id: 2, name: "Naruto", episodes_seen: 220 },
        { id: 3, name: "Black Mirror", episodes_seen: 3 }
      ]
    };
  }
};
</script>

<style>
</style>


