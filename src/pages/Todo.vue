<template>
  <q-page class="q-pa-md">
    <q-list separator bordered>
      <q-item
        v-for="task in tasks"
        :key="task.id"
        @click="task.completed = !task.completed"
        :class="{
          'bg-amber-4': !task.completed,
          'green-5': task.completed,
        }"
        clickable
        v-ripple
      >
        <q-item-section side top>
          <q-checkbox v-model="task.completed" />
        </q-item-section>
        <q-item-section>
          <q-item-label :class="{ 'text-strike': task.completed }">{{
            task.Name
          }}</q-item-label>
        </q-item-section>

        <q-item-section side top>
          <div class="row">
            <div class="col justify-center">
              <q-icon name="event" size="18px" class="q-mr-xs" />
            </div>
            <div class="column">
              <q-item-label class="row justify-end" caption>{{
                task.Date
              }}</q-item-label>
              <q-item-label class="row justify-end" caption>
                <small> {{ task.Time }}</small></q-item-label
              >
            </div>
          </div>
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
import task from "../components/Task.vue";
export default {
  data() {
    return {
      tasks: [
        {
          id: 1,
          Name: "task 1",
          Date: "2021-01-01",
          Time: "10:00",
          completed: false,
        },
        {
          id: 2,
          Name: "task 2",
          Date: "2021-01-01",
          Time: "10:00",
          completed: false,
        },
        {
          id: 3,
          Name: "task 3",
          Date: "2021-01-01",
          Time: "10:00",
          completed: false,
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
