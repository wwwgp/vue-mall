<!--  -->
<template>

<el-tree :data="data" :props="defaultProps" @node-click="handleNodeClick"></el-tree>

</template>

<script>
//这里可以导入其他文件（比如：组件，工具js，第三方插件js，json文件，图片文件等等）
//例如：import 《组件名称》 from '《组件路径》';

export default {
//import引入的组件需要注入到对象中才能使用
components: {},
data() {
      return {
        data: [],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
      };
    },
//监听属性 类似于data概念
computed: {},
//监控data中的数据变化
watch: {},
activated() {
  this.getMenu();
}, //如果页面有keep-alive缓存功能，这个函数会触发
//方法集合
methods: {
  handleNodeClick(data) {
        console.log(data);
      },
          // 获取数据列表
      getMenu () {
        this.$http({
          url: this.$http.adornUrl('/product/category/list/tree'),
          method: 'get'
          }).then(datad =>{
              console.log("成功打印",datad)
          })
      }
},
//生命周期 - 创建完成（可以访问当前this实例）
created() {

},
//生命周期 - 挂载完成（可以访问DOM元素）
mounted() {

},
beforeCreate() {}, //生命周期 - 创建之前
beforeMount() {}, //生命周期 - 挂载之前
beforeUpdate() {}, //生命周期 - 更新之前
updated() {}, //生命周期 - 更新之后
beforeDestroy() {}, //生命周期 - 销毁之前
destroyed() {}, //生命周期 - 销毁完成


}
</script>
<style scoped>


</style>