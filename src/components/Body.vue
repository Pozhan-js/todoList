/* eslint-disable */
<template>
  <div>
    <ul class="todo-main">
      <li v-for="(item, index) of list" :key="item.id">
        <label>
          <input type="checkbox" />
          <span>{{ item.name }}</span>
          <span v-if="item.has">{{ item.has }}</span>
        </label>
        <button
          class="btn btn-danger"
          style="display: block"
          @click="handleAdd(item, index)"
        >
          删除
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    list: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {};
  },
  methods: {
    handleAdd(data, index) {
      // this.list[index] = {
      //   ...data,
      //   has: "xixi",
      // };

      this.$set(data, "name", "xixi");

      console.log(this.list);
      this.$emit("add", data);
    },
  },
  mounted() {
    // this.handleAdd();
    // this.list.push({ name: "hash", id: Date.now(), status: false });
  },
};
</script>

<style>
/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
</style>
