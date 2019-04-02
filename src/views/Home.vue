<template>
  <div :class="$style.homePage">
    <Banner />
    <section :class="[$style.cateList, 'my-0 my-md-4 py-3 py-md-0']">
      <div class="container">
        <div class="row row-10 row-xs-15 flex-nowrap flex-md-wrap">
          <div
            :class="[$style.item, 'col-12 col-sm-6 col-md-3 mt-0 mt-md-4']"
            v-for="item in cates"
            :key="item.id"
          >
            <CateCard :id="item.id" :img="item.img" :name="item.name"/>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style lang="scss" module>
.item {
  height: 147.66px;
}
@media (min-width: 992px) and (max-width: 1199.98px) {
  .item {
    height: 122.3px;
  }
}
@media (min-width: 768px) and (max-width: 991.98px) {
  .item {
    height: 88.6px;
  }
}
@media (max-width: 767.98px) {
  .cateList {
    width: 100%;
    overflow-x: scroll;
    overflow-y: hidden;
    -webkit-overflow-scrolling: touch;
    transform: translate3d(0, 0, 0);
    border-top: 10px solid #f3f3f3;
    border-bottom: 10px solid #f3f3f3;
    .item {
      height: 166px;
      flex: 0 0 95%;
      max-width: 95%;
      padding-right: 0;
      padding-left: 10px;

      &:first-child {
        padding-left: 15px;
      }
      &:last-child {
        padding-right: 15px;
      }
    }
  }
}
</style>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import Banner from "@/components/Banner/index.vue";
import CateCard from "@/components/Card/CateCard/index.vue";

@Component({
  components: {
    Banner,
    CateCard
  }
})
export default class Home extends Vue {
  cates = [
    {
      id: 1,
      name: "故事",
      img: "/img/bg/cate1.jpg"
    },
    {
      id: 2,
      name: "摄影技巧",
      img: "/img/bg/cate2.png"
    },
    {
      id: 3,
      name: "旅行·在路上",
      img: "/img/bg/cate3.jpeg"
    },
    {
      id: 4,
      name: "摄影",
      img: "/img/bg/cate4.jpg"
    },
    {
      id: 5,
      name: "上班那点事",
      img: "/img/bg/cate5.jpg"
    },
    {
      id: 6,
      name: "生活家",
      img: "/img/bg/cate6.jpg"
    },
    {
      id: 7,
      name: "随笔集",
      img: "/img/bg/cate7.jpg"
    },
    {
      id: 8,
      name: "生活着",
      img: "/img/bg/cate8.jpg"
    }
  ];
}
</script>
