<template>
  <div class="banner" :style="{ 'background-image': 'url(' + bg + ')' }">
    <div class="container">
      <div class="row no-gutters">
        <div class="items items-left col-12 col-md-6">
          <div class="item">
            <ArticleCard
              :article-id="left.id"
              :img="left.img"
              :label="left.label"
              :title="left.title"
              :time="left.time"
              :comment="left.comment"
              :like="left.like"
            />
          </div>
        </div>
        <div class="items items-right col-12 col-md-6">
          <div class="item" v-for="item in right" :key="item.id">
            <ArticleCard
              :article-id="item.id"
              :img="item.img"
              :label="item.label"
              :title="item.title"
              :time="item.time"
              :like="item.like"
              :font="
                'font-18 font-md-16 font-sm-16 font-xs-14 light-14 weight-400'
              "
              :sub-font="'font-12'"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
.banner {
  padding: 120px 0 50px 0;
  margin-top: 0 !important;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  background-color: #000;
  position: relative;

  &::before {
    content: "";
    position: absolute;
    background-color: rgba(0, 0, 0, 0.4);
    top: 0;
    left: 0;
    bottom: 0;
    width: 100%;
  }
}
.items-left {
  .item {
    height: 500px;
  }
}
.items-right {
  .item {
    display: block;
    float: left;
    height: 250px;
    width: 50%;
  }
}
</style>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import ArticleCard from "@/components/Card/ArticleCard/index.vue";

@Component({
  components: {
    ArticleCard
  }
})
export default class Banner extends Vue {
  bg = "/img/bg/banner.jpeg";
  left = {
    id: 1,
    img: "/img/bg/main-card.jpeg",
    title: `
      二十岁的年纪，内心身怀雄心壮志，
      却又不得不脚踏实地，做八十岁想起来都会嘴角上扬的事`,
    label: "旅行·在路上",
    time: 1554132473605,
    comment: 1203,
    like: 20
  };
  right = [
    {
      id: 2,
      img: "/img/bg/card1.jpeg",
      title: `
        二十岁的年纪，内心身怀雄心壮志，
        却又不得不脚踏实地，做八十岁想起来都会嘴角上扬的事`,
      label: "旅行·在路上",
      time: 1554132473605,
      comment: 1203,
      like: 20
    },
    {
      id: 3,
      img: "/img/bg/card2.jpeg",
      title: `
        二十岁的年纪，内心身怀雄心壮志，
        却又不得不脚踏实地，做八十岁想起来都会嘴角上扬的事`,
      label: "旅行·在路上",
      time: 1554132473605,
      comment: 1203,
      like: 20
    },
    {
      id: 4,
      img: "/img/bg/card3.jpeg",
      title: `
        二十岁的年纪，内心身怀雄心壮志，
        却又不得不脚踏实地，做八十岁想起来都会嘴角上扬的事`,
      label: "旅行·在路上",
      time: 1554132473605,
      comment: 1203,
      like: 20
    },
    {
      id: 5,
      img: "/img/bg/card4.jpeg",
      title: `
        二十岁的年纪，内心身怀雄心壮志，
        却又不得不脚踏实地，做八十岁想起来都会嘴角上扬的事`,
      label: "旅行·在路上",
      time: 1554132473605,
      comment: 1203,
      like: 20
    },
  ];
}
</script>
