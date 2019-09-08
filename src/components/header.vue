<template>
  <div class="header-wrapper">
    <div v-for="(item, index) in list" class="headerItem" @click="selectItem(item)" :key="index">
      <div class="itemContent" :class="{'selected': item === tabKey}">Event Type {{item}}</div>
      <div class="close" @click.stop="closeTab(item)"> X </div>
    </div>
  </div>
</template>

<script>
export default {
    props: {
        list: {
        },
        setTabIndex: {
        },
        removeKey: {

        },
        tabKey: {

        }
    },
    computed: {
        selectedKey() {
          return  list.findIndex(item=> item===this.tabKey);
        },
    },
    data() {
        return {

        }
        
    },
    methods: {        
        selectItem(item) {
            this.setTabIndex(item);
        },
        closeTab(key) {
            this.removeKey(key);
        }
    }
}
</script>

<style lang="scss" scoped>
.header-wrapper {
  width: 100%;
  height: 100%;
  overflow-x: auto;
  background-color: rgb(149, 153, 154);
  white-space: nowrap;
  .headerItem {
    position: relative;
    display: inline-flex;
    vertical-align: bottom;
    // float: left;
    margin-left: 20px;
    width: 20%;
    height: 90%;
    // margin-top: 10%;
    background-color: white;
    .close {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 10%;
        height: 100%;
    }
    .itemContent {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      &.selected {
          color: red;
      }
      // outline: 1px solid red;
      // background-color: pink;
    }
  }
}
</style>