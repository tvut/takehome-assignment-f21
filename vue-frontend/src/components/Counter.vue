<template>
  <div>
    <p>You have watched {{count}} episodes.</p>
    <button v-on:click="count += 1">Increase Count</button>
    <button v-on:click="count -= 1">Decrease Count</button>
  </div>
</template>

<script>
export default {
  props:['count'],
  data() {
    return {
      count
    };
  }
};
</script>

<style>
</style>

