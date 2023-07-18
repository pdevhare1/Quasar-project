<template>
  <div>
    <div>{{ task.Name }}</div>
    <div>{{ task.Date }} @ {{ task.Time }}</div>
    <button @click="DeleteTask()">X</button>
  </div>
</template>

<script>
export default {
  props: ["task"],
};
</script>

<style></style>
