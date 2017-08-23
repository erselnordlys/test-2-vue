<template xmlns:v-on="http://www.w3.org/1999/xhtml" xmlns:v-bind="http://www.w3.org/1999/xhtml">
    <div id="main">
      <div id="pre-table">
        <div id="pre-table__icon"></div>
        <div id="pre-table__headline">{{msg.headline}}</div>
      </div>
      <my-table></my-table>
      <show-more></show-more>

    </div>
</template>

<script>

  import Table from './Table.vue';
  import ShowMoreButton from './ShowMoreButton.vue'

  export default {
    name: 'Main',
    data () {
      return {
        msg: {
          headline: 'PEOPLE'
        }
      }
    },
    components: {
      'my-table': Table,
      'show-more': ShowMoreButton
    }
  }
</script>

<style scoped>

  #main {
    align-items: center;
    background-color: #f7f9fa;
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: auto;
    margin: 40px 0;
    padding: 22px 70px 78px;
    width: 100%;
  }

  #pre-table {
    align-items: flex-end;
    display: flex;
    justify-content: flex-start;
    margin-bottom: 10px;
    max-width: 1000px;
    width: 100%;
  }

  #pre-table__icon {
    background: url('../assets/icons/people.png') center/ 27px 22px;
    height: 22px;
    width: 22px;
  }

  #pre-table__headline {
    color: #5a5a5a;
    font-size: 17px;
    font-weight: 500;
    margin-left: 5px;
  }
</style>
