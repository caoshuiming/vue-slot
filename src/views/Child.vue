<!-- 子组件-->
<!-- vue slot 是组件的一块html模板 ，这块模板由父组件提供。-->
<!-- 是子组件暴露的一个父组件传入自定义内容的接口-->
<!-- slot分为三类 默认插槽 具名插槽 作用域插槽-->
<!-- 子组件里面插槽用slot标签 来确定渲染位置-->
<template>
  <div class="content" style="color: green">
    <!--  默认插槽-->
    <header class="text">
      <!-- slot的后备内容：作为一个插槽设置具体后备（默认）内容是很有用的。-->
      <!-- 当父组件不添加任何插槽内容时，显示默认值-->
      <slot>默认值</slot>
    </header>
  </div>
</template>

<!--具名插槽用name属性来表示插槽名字，如果不传为默认插槽-->
<!--<template>-->
<!--  <div class="content">-->
<!--    <main class="text">-->
<!--      <slot name="main"></slot>-->
<!--    </main>-->
<!--    <footer class="text">-->
<!--      <slot name="footer"></slot>-->
<!--    </footer>-->
<!--  </div>-->
<!--</template>-->

<!--作用域插槽在作用域上绑定属性来将子组件的信息传给父组件使用-->
<!--这些属性挂在父组件的slot-scope接收对象上-->
<!--作用域插槽 父组件可以访问到子组件的数据 子组件中slot标签上面的特性 称为插槽prop-->
<!--也可以传function-->
<!--<template>-->
<!--  <div class="content">-->
<!--    <footer class="text">-->
<!--      <slot name="footer" :user="user" :testClick="testClick"></slot>-->
<!--    </footer>-->
<!--  </div>-->
<!--</template>-->

<script>
  export default {
    name: "Child",
    data(){
      return{
        user:{
          title:'csm title',
          name:'csm name'
        }
      }
    },
    methods:{
      testClick:function(){
        alert('hello')
      }
    }
  }
</script>

<style scoped>

</style>