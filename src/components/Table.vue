<template xmlns:v-on="http://www.w3.org/1999/xhtml" xmlns:v-bind="http://www.w3.org/1999/xhtml">
    <div id="table">

      <div id="head">
        <div id="user"></div>
        <div id="ideas">{{msg.ideas}}</div>
        <div id="following">{{msg.following}}</div>
        <div id="followers">{{msg.followers}}</div>
      </div>

      <user
        v-for="items in sendData"
        v-bind:data="items"
      ></user>

    </div>
</template>

<script>

  import UserLine from './UserLine.vue'

    export default {
      name: '',
      data () {
        return {
          msg: {
            ideas: 'Ideas',
            following: 'Following',
            followers: 'Followers'
          },
          imagesNumbers: [1, 2, 3, 4, 5],
          names: ['John Adams', 'Kevin Malcolm', 'James Madison', 'James Monroe', 'Andrew Jackson'],
          rates: [102, 1472, 32, 3086, 102],
          ideas: [0, 20, 0, 53, 0],
          following: [50, 19, 2, 1049, 50],
          followers: [0, 26, 0, 45, 0]
        }
      },
      components: {
        user: UserLine
      },
      computed: {
        sendData: function () {
            let arr = [];
            let index = 0;
          for (let i = 0; i < 12; i++) {
              let element = {};
              if (index == 5) {
                  index = 0;
              }
              element.imageNumber = index;
              element.name = this.names[index];
              element.rate = this.rates[index];
              element.ideas = this.ideas[index];
              element.following = this.following[index];
              element.followers = this.followers[index];
              arr.push(element);
              index++;
          }
          return arr;
        }
      }
    }
</script>

<style scoped>

  #table {
    border: 1px solid #bfbfbf;
    border-radius: 4px;
    height: auto;
    max-width: 1000px;
    width: 100%;
  }

  #head {
    background-color: #ecf0f3;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
  }

  #head div {
    height: 29px;
  }

  #head {
    align-items: flex-start;
    display: flex;
    padding: 0 10px;
  }

  #following,
  #followers,
  #ideas {
    align-items: center;
    display: flex;
    font-weight: normal;
    justify-content: flex-end;
    height: 100%;
    min-width: 155px;
    padding-right: 15px;
    text-align: left;
  }

  #user {
    align-items: center;
    display: flex;
    flex-grow: 1;
    justify-content: flex-start;
    height: 100%;
    max-width: 600px;
  }


</style>
