<template>
  <q-page padding>
    <h6>todo page</h6>
  </q-page>
</template>

<script>
import task from "../components/Task.vue";
export default {
  data() {
    return {
      tasks: [
        {
          Name: "Go to the store",
          Date: "2021-01-01",
          Time: "10:00",
          id: 1,
        },
        {
          Name: "Go to the Home",
          Date: "2021-01-02",
          Time: "13:00",
          id: 2,
        },
        {
          Name: "food",
          Date: "2021-01-03",
          Time: "14:00",
          id: 3,
        },
      ],
    };
  },
  methods: {
    DeleteMsg(index) {
      this.tasks.splice(index, 1);
    },
  },
  components: {
    task,
  },
};
</script>
<style></style>
