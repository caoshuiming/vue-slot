<!--父组件 默认插槽-->
<template>
  <div class="container">
    <child>
      <p>哈哈哈哈哈，我就是不出现</p>
      <template v-slot:default>
        但如果你定义了 default 之后，其他内容就不会出现了，原理同上，不能重复定义
      </template>
    </child>
    <!--独占默认插槽的缩写-->
    <child v-slot="slotProps">
      当只有默认插槽时，此为独占默认插槽的缩写<br>
      如果组件中有其他具名插槽，这么写会报错<br>
      slotProps取的是，子组件标签slot上属性数据的集合
    </child>
  </div>
</template>

<!--父组件 具名插槽-->
<!--<template>-->
<!--  <div class="container">-->
<!--    <child>-->
<!--      <template v-slot:main>-->
<!--        <a href="https://www.baidu.com" target="_blank">百度</a>-->
<!--      </template>-->
<!--      <template #footer>-->
<!--        页脚（v-slot:的缩写#）-->
<!--      </template>-->
<!--      <template #footer>-->
<!--        只占了一个位置，写两个或以上就会以最后一个为准-->
<!--      </template>-->
<!--    </child>-->
<!--  </div>-->
<!--</template>-->

<!--父组件 作用域插槽-->
<!--<template>-->
<!--  <div class="container">-->
<!--    <child>-->
<!--      <template #footer="slotProps">-->
<!--        {{slotProps.user.title}}-->
<!--        <button @click="slotProps.testClick">点我</button>-->
<!--      </template>-->
<!--      <template #footer="{user,testClick}">-->
<!--        {{user.title}}<br>-->
<!--        此为解构插槽prop<br>-->
<!--        &lt;!&ndash; 子组件中的通用方法，可传递给父组件复用&ndash;&gt;-->
<!--        <button @click="testClick">点我</button>-->
<!--      </template>-->
<!--    </child>-->
<!--  </div>-->
<!--</template>-->
<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import child from './Child.vue'

export default {
  name: 'Home',
  components: {
    child
  }
}
</script>
