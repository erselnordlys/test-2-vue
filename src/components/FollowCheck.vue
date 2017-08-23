<template xmlns:v-on="http://www.w3.org/1999/xhtml" xmlns:v-bind="http://www.w3.org/1999/xhtml">
    <div id="follow-check">
      <div
        class="plus"
        @mouseover="show = true"
        v-if="showPlus"
      ></div>

      <div
        class="check"
        @mouseover="show = true"
        v-if="showCheck"
      ></div>

      <div
        class="follow"
        v-if="showFollow"
        @mouseleave="show = false"
        @click="clickButton"
      >{{msg.follow}}</div>

      <div
        class="unfollow"
        v-if="showUnfolllow"
        @mouseleave="show = false"
        @click="clickButton"
      >{{msg.unfollow}}</div>

    </div>
</template>

<script>

  import Plus from '../assets/icons/plus.png';
  import Check from '../assets/icons/plus.png';

  export default {
    name: 'FollowCheck',
    data () {
      return {
        msg: {
          follow: 'Follow',
          unfollow: 'Unfollow'
        },
        showFollowButton: true,
        showUnfollowButton: false,
        showCheck: false,
        showPlus: true,
        show: ''
      }
    },
    methods: {
      clickButton: function () {
        this.showCheck = !this.showCheck;
        this.showPlus = !this.showPlus;
        this.showFollowButton = !this.showFollowButton;
        this.showUnfollowButton = !this.showUnfollowButton;
      }
    },

    computed: {
      showFollow: function () {
        return this.show && this.showFollowButton;
      },

      showUnfolllow: function () {
        return this.show && this.showUnfollowButton;
      }
    }


    }
</script>

<style scoped>

  #follow-check {
    align-self: flex-start;
    height: 15px;
    margin-left: 10px;
    margin-top: 8px;
    position: relative;
    width: auto;
  }

  #follow-check div {
    cursor: pointer;
    height: 15px;
  }

  .plus {
    background: url('../assets/icons/plus.png') center /16px 15px;
    cursor: pointer;
    display: flex;
    width: 16px;
  }

  .check {
    background: url('../assets/icons/ok.png') center /16px 15px;
    cursor: pointer;
    display: flex;
    width: 13px;
  }

  .follow,
  .unfollow{
    align-items: center;
    animation: buttonAppear 0.2s;
    background-color: #a4c574;
    border-radius: 25px;
    color: white;
    cursor: pointer;
    display: flex;
    font-size: 12px;
    justify-content: center;
    left: 0;
    position: absolute;
    top: 0;
    width: 60px;
  }

  .unfollow {
    background-color: #953a3a;
  }

</style>
