<template>
  <q-page padding>
    <input v-model="Msg" />
    <button @click="clear">clear</button>
    <h5>{{ Msg }}</h5>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      Msg: "I am a message",
    };
  },
  methods: {
    clear() {
      this.Msg = "";
    },
  },
};
</script>
