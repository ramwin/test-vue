<template>
  <div id="app">
    <myComponent />
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
  </div>
</template>

<script>
import myComponent from "ramwin-vue"
export default {
  name: 'App',
  components: {
    myComponent
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
        data: [
          { name: "张三", id: 1, },
          { name: "李四", id: 2, },
        ],
        columns: [
          {field: 'id', title: "编号",},
          {field: 'name', title: "姓名",},
        ],
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
