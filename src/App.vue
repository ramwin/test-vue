<template>
  <div id="app">
    <h1>测试vxe-grid</h1>
    <vxe-grid
      v-bind="gridOptions"
    >
      <template v-slot:title>
        <span>我是自定义的title</span>
      </template>
      <template v-slot:customersearch>
        <span>我是自定义的搜索</span>
      </template>
    </vxe-grid>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      gridOptions: {
        formConfig: {
          items: [
            {
              field: "search",
              title: "默认的搜索",
              itemRender: {
                name: "$input",
              },
            },
            {
              field: "customersearch",
              title: "自定义的搜索",
              slots: {
                title: "title",
                default: "customersearch",
              },
            },
          ]
        },
      },
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
