<template>
  <div>
    <preloader-page />
    <form-list @create="addNote"></form-list>
    <task-list :zadachi="zadachi" @remove="deleteNote"></task-list>
    <div class="tasks">
      <div class="tasks1" @click="setFilterActive('active')">Активные</div>
      <div class="tasks2" @click="setFilterAll('all')">Все</div>
      <div class="tasks3" @click="setFilterCompleted('completed')">
        Завершенные
      </div>
    </div>
  </div>
</template>

<script>
import formList from "../components/formList.vue";
import preloaderPage from "../components/preloaderPage.vue";
import taskList from "../components/taskList.vue";
export default {
  components: { formList, taskList, preloaderPage },
  data() {
    return {
      zadachi: [],
      innerData: {
        activeFilter: "",
      },
    };
  },

  methods: {
    async getTodo() {
      let res = await fetch(
        "https://my-json-server.typicode.com/falk20/demo/todos"
      );
      let result = await res.json();

      this.zadachi = result;
    },

    addNote(lists) {
      this.zadachi.push(lists);
    },

    deleteNote(id) {
      const idx = this.zadachi.findIndex((item) => item.id == id);
      this.zadachi.splice(idx, 1);
    },
  },

  mounted() {
    this.getTodo();
  },
};
</script>

<style lang="scss" scoped>
.tasks {
  margin-top: 20px;
  font-size: 24px;
  cursor: pointer;
}

.tasks1:hover {
  opacity: 0.6;
}

.tasks2:hover {
  opacity: 0.6;
}

.tasks3:hover {
  opacity: 0.6;
}
</style>
