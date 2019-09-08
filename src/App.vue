<template>
  <div id="app">
    <div class="main-wrapper">
    <sideBar class="sideMenu" :setTabIndex="setTabIndex" :list="sideBarList"></sideBar>
    <div class="rightScreen">
      <header1 class="header" :setTabIndex="setTabIndex" :removeKey="removeKey" :list="headerList" :tabKey="selectedTabKey"></header1>
      <sideviewScreen class="screen" :list="eventData[selectedTabKey]"></sideviewScreen>
    </div>
    </div>
  </div>
</template>

<script>
import sideBar from "./components/sideBar.vue";
import header1 from "./components/header.vue";
import sideviewScreen from "./components/sideviewScreen.vue";

export default {
  name: "app",
  mounted() {
    this.sideBarList = Object.keys(this.eventData);
  },
  data() {
    return {
      selectedTabKey: -1,
      sideBarList: [],
      headerList: [],
      eventData: {
        1: [
          { timeStamp: "111111110", raw: "first one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        2: [
          { timeStamp: "111111110", raw: "second one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        3: [
          { timeStamp: "111111110", raw: "third one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        4: [
          { timeStamp: "111111110", raw: "first one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        5: [
          { timeStamp: "111111110", raw: "second one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        6: [
          { timeStamp: "111111110", raw: "third one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        7: [
          { timeStamp: "111111110", raw: "first one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        8: [
          { timeStamp: "111111110", raw: "second one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        9: [
          { timeStamp: "111111110", raw: "third one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        10: [
          { timeStamp: "111111110", raw: "first one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        11: [
          { timeStamp: "111111110", raw: "second one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
        12: [
          { timeStamp: "111111110", raw: "third one0" },
          { timeStamp: "111111111", raw: "first one1" },
          { timeStamp: "111111112", raw: "first one2" },
          { timeStamp: "111111113", raw: "first one3" },
          { timeStamp: "111111114", raw: "first one4" },
          { timeStamp: "111111115", raw: "first one5" },
          { timeStamp: "111111116", raw: "first one6" },
          { timeStamp: "111111117", raw: "first one7" },
          { timeStamp: "111111118", raw: "first one8" },
          { timeStamp: "111111119", raw: "first one9" },
          { timeStamp: "1111111110", raw: "first one10" },
          { timeStamp: "1111111111", raw: "first one11" },
          { timeStamp: "1111111112", raw: "first one12" },
          { timeStamp: "1111111113", raw: "first one13" },
          { timeStamp: "1111111114", raw: "first one14" }
        ],
      }
    };
  },
  methods: {
    setTabIndex(key) {
      this.selectedTabKey = key;
      if (!this.headerList.includes(key)) {
        this.headerList.push(key);
      }
      console.log('1111', key, this.eventData[key]);
    },
    removeKey(key) {
      let idx = this.headerList.indexOf(key);
      
      console.log('key', key, '  ', idx);
      if (key === this.selectedTabKey) {
        if (idx < this.headerList.length - 1) {
      console.log('key111', key, '  ', idx);
          this.selectedTabKey = this.headerList[idx + 1];
        } else {
      console.log('key2222  ', key, '  ', idx);
          this.selectedTabKey = this.headerList[idx - 1];
          console.log('3333333', this.selectedTabKey);
        }
      }
      console.log("before", this.headerList);
      this.headerList = [...this.headerList];
      this.headerList.splice(idx, 1);
      console.log("after", this.headerList, idx);

    }
  },
  components: {
    sideviewScreen,
    header1,
    sideBar
  }
};
</script>

<style>
</style>
<style lang="scss" scoped>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  // margin-top: 60px;
  .main-wrapper {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
  outline: 1px solid gray;
  .sideMenu {
    position: relative;
    width: 20%;
    height: 100%;
    top: 0;
    left: 0;
    display: inline-block;
    // background-color: gray;
    vertical-align: top;
  }
  .rightScreen {
    position: relative;
    width: 77%;
    height: 100%;
    display: inline-block;
    vertical-align: top;
    margin-left: 1%;
    .header {
      position: relative;
      width: 100%;
      height: 10%;
      // outline: 1px solid red;
    }
    .screen {
      position: relative;
      width: 100%;
      height: 90%;
      // overflow: hidden;
      // background-color: reds;
    }
  }
  }
}
    ::-webkit-scrollbar {
width: 0px;  /* Remove scrollbar space */
background: transparent;  /* Optional: just make scrollbar invisible */
}

</style>
