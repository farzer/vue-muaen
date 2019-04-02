<template>
  <a :class="$style.wrap" :href="'/cate/' + id">
    <div
      :class="$style.customHoverImg"
      :style="{ 'background-image': 'url(' + img + ')' }"
    />
    <div :class="$style.content">
      <h2 :class="[$style.h2, font]">
        {{ name }}
      </h2>
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
  border-radius: 10.56px;
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
      opacity: 0;
    }
    .h2 {
      font-weight: 500 !important;
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
  display: flex;
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    to bottom,
    transparent 0,
    rgba(0, 0, 0, 0.7) 100%
  );
  z-index: 1;
  color: #fff;
  justify-content: center;
  align-items: center;
}

.h2 {
  display: flex;
  margin: 0;
  word-wrap: break-word;
}
</style>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component({})
export default class CateCard extends Vue {
  @Prop(Number) readonly id!: number;
  @Prop(String) readonly img!: string;
  @Prop(String) readonly name!: string;
  @Prop({
    default: "font-18 font-md-16 font-xs-20 weight-400"
  })
  readonly font!: string;
}
</script>
