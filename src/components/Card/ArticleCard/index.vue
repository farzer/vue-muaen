<template>
  <a :class="$style.wrap" :href="'/article/' + articleId">
    <div
      :class="$style.customHoverImg"
      :style="{ 'background-image': 'url(' + img + ')' }"
    />
    <div :class="$style.content">
      <div :class="$style.title">
        <h2 :class="[$style.h2, font]">
          {{ title }}
        </h2>
      </div>
      <div :class="[$style.data, subFont]">
        <div :class="$style.label">{{ label }}</div>
        <div :class="$style.extra">
          <span :class="$style.time">{{ time | formatTime }}</span>
          <span :class="$style.comment" v-if="comment">{{ comment }}</span>
          <span :class="$style.like">{{ like }}</span>
        </div>
      </div>
    </div>
  </a>
</template>

<style lang="scss" module>
.wrap {
  display: block;
  position: relative;
  vertical-align: top;
  height: 100%;
  width: 100%;
  overflow: hidden;

  &::before {
    content: "";
    position: absolute;
    background-color: rgba(21, 21, 21, 0.66);
    bottom: 0;
    left: 0;
    right: 0;
    top: 0;
    z-index: 1;
    opacity: 0.33;
    transition: all 1s ease 0s;
  }

  &:hover {
    .customHoverImg {
      transform: scale(1.05);
    }

    &::before {
      opacity: 0.11;
    }
  }
}
.customHoverImg {
  display: block;
  width: 100%;
  height: 100%;
  position: relative;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  transform-origin: center;
  transition: all 444ms ease-in-out;
}
.content {
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  background: linear-gradient(
    to bottom,
    transparent 0,
    rgba(0, 0, 0, 0.7) 100%
  );
  z-index: 1;
  padding: 24px;
  color: #fff;
}
.title {
  overflow: hidden !important;
  text-overflow: ellipsis !important;
  display: -webkit-box !important;
  -webkit-line-clamp: 2 !important;
  -webkit-box-orient: vertical !important;
}
.h2 {
  margin: 0;
  word-wrap: break-word;
}
.data {
  margin-top: 16px;
  font-size: 14px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.label {
  display: flex;
  flex: 1;
}
.extra {
  display: flex;
  flex-wrap: nowrap;
  overflow: hidden;
}
.comment,
.like {
  margin-left: 10px;
}
</style>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import moment from "moment";

@Component({
  filters: {
    formatTime: (value: number) => moment(value).format("YYYY-MM-DD")
  }
})
export default class ArticleCard extends Vue {
  @Prop(Number) readonly articleId!: number;
  @Prop(String) readonly img!: string;
  @Prop(String) readonly title!: string;
  @Prop(String) readonly label!: string;
  @Prop(Number) readonly time!: number;
  @Prop(Number) readonly comment!: number;
  @Prop(Number) readonly like!: number;
  @Prop({
    default: "font-24 font-md-20 font-xs-20 light-14 weight-400"
  })
  readonly font!: string;
  @Prop({
    default: "font-14 font-md-12"
  })
  readonly subFont!: string;
}
</script>
