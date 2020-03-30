<template>
  <div class="nav-bar-item" @click="itemClick">
    <div :style="{color: color}">
      <slot></slot>
      <slot name="title-text">
        <div>{{title}}</div>
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NavBarItem',
  props: {
    title: {
      type: String,
      default: ''
    },
    path: {
      type: String,
      default: ''
    },
    textColor: {
      type: String,
      default: '#666'
    },
    activeColor: {
      type: String,
      default: '#ff8198'
    }
  },
  computed: {
    isActive () {
      return this.$route.path.indexOf(this.path) !== -1
    },
    color () {
      return this.isActive ? this.activeColor : this.textColor
    }
  },
  methods: {
    itemClick () {
      this.$router
        .replace(this.path)
        .catch(err => err) // fix vue-router 3.1.X bug: Navigating to current location is not allowed
    }
  }
}
</script>

<style scoped>
.nav-bar-item {
  flex: 1;
  text-align: center;
  height: 49px;
  font-size: 14px;
  margin-top: 3px;
}
</style>
