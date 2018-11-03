<template>
  <nav>
    <div><span>锅炉温控智能系统</span> <span>Powered by: LeapAI.com</span></div>
  </nav>
</template>

<script>
import { mapActions } from 'vuex'

export default {
  methods: {
    ...mapActions('layout', [
      'showCart'
    ]),

    openCart () {
      this.showCart(true)
    },
  },
}
</script>

<style lang="less" scoped>
@import "style/imports";

nav {
  background: @app-color;
  display: flex;
  flex-direction: row;
  align-items: center;
  color: white;
  background-color: rgb(48, 142, 204);
  height: 70px;
  line-height: 70px;
  >div{
    width: 1200px;
    margin: 0 auto;
    position: relative;
    >span:first-child{
      float: left;
      font-size: 28px;
    }
    >span:last-child{
      position: absolute;
      right: 0;
      bottom: -20px;
    }
  }
  > * {
    flex: 0 0 auto;
  }

  a {
    color: white;
    display: inline-block;
    padding: 16px 28px;
    border-radius: 3px 3px 0 0;

    &:hover {
      background: lighten(@app-color, 10%);
    }

    &.router-link-active {
      background: @page-background;
      color: @app-color;
    }
  }
}

.app-title {
  font-size: 1.3rem;
  padding: 0 18px;
}

.actions {
  flex: 1 1 auto;
  text-align: right;
  padding: 4px 12px;
}

</style>
