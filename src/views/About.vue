<template>
  <div class="home">
    <div class="tab">
      <template v-for="(item, index) in bannerList">
        <div
          class="tabs"
          :class="{ active: index === active }"
          :key="item.id"
          @click="active = index"
        >
          {{ index }}
        </div>
      </template>
    </div>
    <div v-for="(item, index) in bannerList" :key="item.id + index">
      <template v-if="item.show">
        <HelloWorld
          v-show="index === active"
          :index="index"
          :list="item.list"
        />
      </template>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorlds.vue";

export default {
  name: "Home",
  components: {
    HelloWorld
  },
  data() {
    return {
      active: 0,
      bannerList: [
        {
          id: "one",
          show: true,
          list: [
            "http://qiniu.dktoo.com/uPic/1578729021590.jpg",
            "http://qiniu.dktoo.com/uPic/1578639060468.png",
            "http://qiniu.dktoo.com/uPic/1578639060643.png"
          ]
        },
        {
          id: "two",
          show: true,
          list: [
            "http://qiniu.dktoo.com/uPic/1578729021590.jpg",
            "http://qiniu.dktoo.com/uPic/1578639060468.png",
            "http://qiniu.dktoo.com/uPic/1578639060643.png"
          ]
        },
        {
          id: "three",
          show: true,
          list: [
            "http://qiniu.dktoo.com/uPic/1578729021590.jpg",
            "http://qiniu.dktoo.com/uPic/1578639060468.png",
            "http://qiniu.dktoo.com/uPic/1578639060643.png"
          ]
        }
      ]
    };
  }
};
</script>
<style lang="scss" scoped>
.tab {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 15px;
  box-sizing: border-box;
  .tabs {
    background-color: #eee;
    margin: 0 5px;
    padding: 5px 10px;
    box-sizing: border-box;
    cursor: pointer;
  }
  .active {
    color: #fff;
    background-color: red;
  }
}
</style>
