<template>
  <div>
    <div>
      <input v-model="inputValue" />
      <button v-on:click="handleSubmit">submit</button>
    </div>

    <ul>
      <todoitem v-for="(item,index) of list" v-bind:key="index" v-bind:content="item" v-bind:index="index" v-on:delete="handleDelete"></todoitem>
    </ul>
  </div>
</template>

<script>

import todoItem from './components/todoItem'

export default {
  components: {
    'todoitem': todoItem
  },
  data () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleSubmit () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
