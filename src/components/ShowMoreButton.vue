<template xmlns:v-on="http://www.w3.org/1999/xhtml" xmlns:v-bind="http://www.w3.org/1999/xhtml">
    <div id="show-more">
      {{msg}}
    </div>
</template>

<script>

  export default {
    name: '',
    data () {
      return {
        msg: 'SHOW MORE'
      }
    }
  }
</script>

<style scoped>

  #show-more {
    align-items: center;
    background-color: #ffffff;
    border: 1px solid #bfbfbf;
    border-bottom-left-radius: 4px;
    border-bottom-right-radius: 4px;
    border-top: 1px dashed #bfbfbf;
    cursor: pointer;
    display: flex;
    font-size: 10px;
    font-weight: 900;
    height: 26px;
    justify-content: center;
    margin-top: -1px;
    width: 172px;
  }

</style>
