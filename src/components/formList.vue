<template>
  <div>
    <form @submit.prevent class="form" action="">
      <input
        type="text"
        placeholder="Название"
        required="required"
        v-model="list.text"
      />
      <input
        type="text"
        placeholder="Статус"
        required="required"
        v-model="list.active"
      />
      <button class="btn" @click="createNote" :disabled="isBtnDisabled">
        Добавить в задачу
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: {
        text: "",
        active: "",
      },
    };
  },

  computed: {
    isBtnDisabled() {
      return this.list.text.legth === 0 || this.list.active.length === 0;
    },
  },

  methods: {
    createNote() {
      this.list.id = Date.now();
      this.$emit("create", this.list);
      this.list = {
        title: "",
        text: "",
        active: "",
      };
    },
  },
};
</script>

<style lang="scss" scoped>
.form {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
}

input {
  min-height: 60px;
  border: 1px solid teal;
  border-radius: 10px;
  margin-top: 10px;
  font-size: 18px;
  padding: 10px;
}

.btn {
  font-size: 18px;
  color: black;
  border: 2px solid teal;
  background: none;
  max-width: 200px;
  min-height: 40px;
  border-radius: 10px;
  margin-top: 30px;
}

.btn:active {
  background: black;
  color: white;
  border: none;
}

input:valid ~ button:hover {
  opacity: 0.6;
  cursor: pointer;
}

input:invalid ~ button {
  color: #b4b4b4;
  background-color: #eeeeee;
}
</style>
