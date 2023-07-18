<template>
  <q-page padding>
    <!-- <button class="btn" @click="number++">
      {{ number }}
    </button> -->
    <q-btn outline style="color: goldenrod" class="btn" @click="number++">{{
      number
    }}</q-btn>
    <input v-model="Msg" @keyup.esc="clear" @keyup.enter="alertMsg" />
    <button @click="clear">clear</button>
    <h5 class="Border" v-if="Msg.length">{{ Msg }}</h5>
    <h5 v-else>No Msg 😔</h5>
    <hr />
    <p>UpperCase Msg: {{ UpperCaseMsg }}</p>
    <p>LowerCase Msg: {{ Msg }}</p>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      Msg: "I am a message",
      number: 0,
    };
  },
  computed: {
    UpperCaseMsg() {
      return this.Msg.toUpperCase();
    },
  },
  methods: {
    clear() {
      this.Msg = "";
    },
    keyup(e) {
      console.log(e);
      if (e.keyCode === 27) {
        this.Msg = "";
      } else if (e.keyCode === 13) {
        this.alertMsg();
      }
    },
    alertMsg() {
      alert(this.Msg);
    },
    show() {
      if (this.Msg.length > 1) {
        return this.Msg;
      }
    },
  },
  filters: {
    LowerCase(value) {
      return value.toLowerCase();
    },
  },
};
</script>
<style>
.Border {
  border: 1px solid black;
  padding: 10px;
  margin: 10px;
}

.btn {
  position: absolute;
  right: 10px;
}
</style>
