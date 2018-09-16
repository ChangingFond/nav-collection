<template>
  <div id="app" class="container">
    <router-view class="router-view"></router-view>
  </div>
</template>
<script>
  import 'ASSET/scss/mreset.scss'
  export default {
    mounted () {
    },
    data: () => ({
      transitionName: '',
      alert: {}
    }),
    watch: {
    },
    methods: {
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
  @import './assets/scss/mixin.scss';
  a {
      color: $font1;
  }
  .right {
      transition: margin 1s;
  }
  .left {
      width: 250px;
      position: fixed;
      top: 0;
      left: -60%;
      height: 100%;
      overflow: auto;
      background: $bgcl;
      z-index: 999;
      transition: left 2s;
      @media (max-width: 768px){
          display: none;
      }
      .nav-element {
          cursor: pointer;
          // margin: 1px;
          padding: 5px 0 7px 0;
          color: $btn;
          transition: color 0.25s;
          svg{
              margin-right: 6px;
          }
      }

      .navbar-active {
          color: $btna;
      }

      .nav-label {
          font-size: 14px;
          padding-left: 70px;
          svg{
              width: 16px;
              height: 16px;
          }
      }
      li{
          width: 100%;
      }
      li:hover{
          opacity: 1;
          background-color: #1e2b3a;
      }
  }
  .modal-active{
      .blur{
          filter: blur(size(3));
      }
  }
  #loading{
      display: none;
  }
  .container,.router-view{
      width: 100%;
      height: 100%;
      box-sizing: border-box;
      // overflow: scroll;
  }
  .icon {
      width: 20px;
      height: 20px;
      vertical-align: text-bottom;
      fill: currentColor;
      overflow: hidden;
  }
  // vue-router transition
  .router-view {
      // width: 100%;
      // animation-duration: 0.5s;
      // animation-fill-mode: both;
      // backface-visibility: hidden;
  }
  .vux-pop-out-enter-active,
  .vux-pop-out-leave-active,
  .vux-pop-in-enter-active,
  .vux-pop-in-leave-active {
      will-change: transform;
      height: 100%;
      position: absolute;
      left: 0;
  }
  .vux-pop-out-enter-active {
      animation-name: popInLeft;
  }
  .vux-pop-out-leave-active {
      animation-name: popOutRight;
  }
  .vux-pop-in-enter-active {
      perspective: 1000;
      animation-name: popInRight;
  }
  .vux-pop-in-leave-active {
      animation-name: popOutLeft;
  }
  @keyframes popInLeft {
      from {
          opacity: 0;
          transform: translate3d(-100%, 0, 0);
      }
      to {
          opacity: 1;
          transform: translate3d(0, 0, 0);
      }
  }
  @keyframes popOutLeft {
      from {
          opacity: 1;
      }
      to {
          opacity: 0;
          transform: translate3d(-100%, 0, 0);
      }
  }
  @keyframes popInRight {
      from {
          opacity: 0;
          transform: translate3d(100%, 0, 0);
      }
      to {
          opacity: 1;
          transform: translate3d(0, 0, 0);
      }
  }
  @keyframes popOutRight {
      from {
          opacity: 1;
      }
      to {
          opacity: 0;
          transform: translate3d(100%, 0, 0);
      }
  }
</style>
