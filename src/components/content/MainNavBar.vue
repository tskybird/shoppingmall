<template>
  <nav-bar>
    <nav-bar-item
    v-for="item in title"
    :title="item.text"
    :path="item.path"
    :key="item.tex"
    active-color="#F56C6C"
    >
      <i :class="[item.iconClass]"></i>
    </nav-bar-item>
  </nav-bar>
</template>

<script>
import NavBar from '../common/NavBar'
import NavBarItem from '../common/NavBarItem'

export default {
  name: 'MainNavBar',
  components: {
    NavBar,
    NavBarItem
  },
  data () {
    return {
      title: {
        home: {
          iconClass: 'icon-home',
          text: '首页',
          path: '/home'
        },
        category: {
          iconClass: 'icon-category',
          text: '分类',
          path: '/category'
        },
        shoppingCart: {
          iconClass: 'icon-shopping-cart',
          text: '购物车',
          path: '/shoppingcart'
        },
        user: {
          iconClass: 'icon-user',
          text: '我的',
          path: '/user'
        }
      }
    }
  }
}
</script>

<style scoped>
</style>
