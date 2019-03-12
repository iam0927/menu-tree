<template>
    <li>
      <span class="span" @click="toggle(model.menuCode)">点击</span>
      <span>{{model.menuName}}</span>
      <ul v-show="open" v-if="hasChild">
        <self-tree v-for="item in treeChild" :key="item.index" :model="item"/>
      </ul>
    </li>
</template>

<script>
import m1 from './m1'
import m2 from './m2'
import m3 from './m3'
import m4 from './m4'
import m5 from './m5'
export default {
  name: 'selfTree',
  props: ['model'],
  data () {
    return {
      treeChild: [],
      open: true
    }
  },
  methods: {
    toggle (menuCode) {
      if (this.treeChild.length) {
        this.open = !this.open
      } else {
        setTimeout(() => {
          if (menuCode === 10) {
            this.treeChild = m1
          } else if (menuCode === 22) {
            this.treeChild = m2
          } else if (menuCode === 30) {
            this.treeChild = m3
          } else if (menuCode === 7) {
            this.treeChild = m4
          } else if (menuCode === 339) {
            this.treeChild = m5
          }
        }, 500)
      }
    }
  },
  computed: {
    hasChild () {
      return this.treeChild.length
    }
  }
}
</script>

<style scoped lang="less">
ul {
  margin-top: 5px;
  li {
    width: 120px;
    margin-bottom: 5px;
    cursor: pointer;
    border: 1px solid #000;
    span.span {
      color: aqua;
      background: yellowgreen;
    }
  }
}
</style>
