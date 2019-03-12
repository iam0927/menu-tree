<template>
  <div>
    <ul v-for="item in demoData" :key="item.index">
      <menu-tree :model="item"></menu-tree>
    </ul>
  </div>
</template>

<script>
import menuTree from './treeChild'
export default {
  components: {
    menuTree
  },
  data () {
    return {
      demoData: [
        {
          id: 1,
          menuName: '基础管理',
          menuCode: 10
        },
        {
          id: 2,
          menuName: '商品管理',
          menuCode: 22
        },
        {
          id: 3,
          menuName: '订单管理',
          menuCode: 30
        },
        {
          id: 4,
          menuName: '商家管理',
          menuCode: 7
        }
      ]
    }
  }
}
</script>

<style scoped lang="less">
div {
  text-align: center;
  ul {
    display: flex;
    align-items: center;
  }
}
</style>
