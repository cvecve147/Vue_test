<template>
  <div>
    <div>
      <input
        type="text"
        v-model="inputValue"
        class="item"
      >
      <button @click="handleSubmit">提交</button>
    </div>
    <ul>
      <todo-item
        v-for="(item,index) of list"
        :content="item"
        :key="index"
        :index="index"
        @del="handleDel"
      ></todo-item>
    </ul>
  </div>

</template>

<script>
  import Todoitem from "./components/Todoitem";
  export default {
    components: { "todo-item": Todoitem },
    data() {
      return {
        inputValue: "",
        list: []
      };
    },
    methods: {
      handleSubmit() {
        this.list.push(this.inputValue);
        this.inputValue = "";
      },
      handleDel(index) {
        this.list.splice(index, 1);
      }
    }
  };
</script>

<style>
</style>
