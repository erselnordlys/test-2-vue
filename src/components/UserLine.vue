<template xmlns:v-on="http://www.w3.org/1999/xhtml" xmlns:v-bind="http://www.w3.org/1999/xhtml">
    <div
      id="main"
    >
      <div class="user-data">
        <div class="photo" v-bind:style="{background: 'url(' + img + ') center /cover'}"></div>
        <div class="column">
          <div class="name">{{name}}</div>
          <div class="stats">
            <div class="stats-icon"></div>
            <div class="stats-num">{{rate}}</div>
          </div>
        </div>

        <follow-check></follow-check>
      </div>

      <div class="ideas">{{ideas}}</div>
      <div class="following">{{following}}</div>
      <div class="followers">{{followers}}</div>
    </div>
</template>

<script>

  import FollowCheck from './FollowCheck.vue';
  import Pic1 from '../assets/images/1.png'
  import Pic2 from '../assets/images/2.png'
  import Pic3 from '../assets/images/3.png'
  import Pic4 from '../assets/images/4.png'
  import Pic5 from '../assets/images/5.png'


  export default {
    name: '',
    data () {
      return {
              name: this.data.name,
              rate: this.data.rate,
              ideas: this.data.ideas,
              following: this.data.following,
              followers: this.data.followers,
              image: [Pic1, Pic2, Pic3, Pic4, Pic5]
            }
    },
    props: ['data'],
    computed: {
      img: function () {
        return this.image[this.data.imageNumber];
      }
    },
    components: {
      'follow-check': FollowCheck
    }
  }
</script>

<style scoped>

  #main {
    align-items: center;
    background-color: #ffffff;
    border-bottom: 1px solid #f1f1f1;
    display: flex;
    height: 60px;
    padding: 0 10px;
  }

  .user-data {
    align-items: center;
    display: flex;
    flex-grow: 1;
    justify-content: flex-start;
    height: 100%;
    max-width: 600px;
  }

  .user-data:nth-child(even) {
    background-color: #fbfbfb;

  }

  #main:last-child {
    border-bottom: none;
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
  }

  .photo {
    border-radius: 3px;
    cursor: pointer;
    height: 50px;
    width: 50px;
  }

  .column {
    align-items: flex-start;
    display: flex;
    flex-direction: column;
    height: 45px;
    justify-content: space-between;
    padding-left: 10px;
  }

  .name {
    color: #2c76c7;
    cursor: pointer;
    font-size: 13px;
    font-weight: bold;
  }

  .stats {
    align-items: flex-end;
    display: flex;
    flex-direction: row;
  }

  .stats-icon {
    background: url('../assets/icons/stats.png') top left / 16px 17px no-repeat;
    height: 18px;
    width: 16px;
  }

  .stats-num {
    font-size: 17px;
    margin-left: 4px;
  }

  .following,
  .followers,
  .ideas {
    align-items: center;
    display: flex;
    font-weight: normal;
    justify-content: flex-end;
    height: 100%;
    min-width: 155px;
    padding-right: 15px;
    text-align: left;
  }


</style>
