<template>
  <div v-if="zadachi.length > 0">
    <div class="flex">
      <div class="flex__card" v-for="post in zadachi" v-bind:key="post.id">
        <div class="flex__card__tasks">Название: {{ post.text }}</div>
        <div class="flex__card__tasks">Статус: {{ post.active }}</div>
        <button class="btn" @click="removeItem(post.id)">Remove</button>
      </div>
    </div>
  </div>
  <div v-else>
    <h2 class="heading">Список задач пуст ....</h2>
  </div>
</template>

<script>
export default {
  props: ["zadachi"],

  methods: {
    removeItem(id) {
      this.$emit("remove", id);
    },
  },
};
</script>

<style lang="scss" scoped>
.flex {
  display: flex;
  gap: 20px;
  margin-top: 50px;
}

.flex__card {
  border: 2px solid teal;
  padding: 10px;
  border-radius: 10px;
}

.flex__card__tasks {
  margin-top: 5px;
  font-size: 24px;
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
  cursor: pointer;
}

.btn:hover {
  opacity: 0.6;
}

.btn:active {
  background: black;
  color: white;
  border: none;
}

.heading {
  color: rgb(193, 26, 26);
  text-align: center;
}
</style>
