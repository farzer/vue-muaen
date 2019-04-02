<template>
  <header :class="$style.wrap">
    <div class="container">
      <div :class="$style.navbar">
        <a :class="[$style.brand, 'font-24 font-md-22 font-sm-20']" href="/">
          MUAEN
        </a>
        <div :class="$style.collapse">
          <ul :class="$style.navs">
            <li :class="$style.nav">
              <router-link to="/" :class="$style.navLink">首页</router-link>
            </li>
            <li :class="$style.nav">
              <router-link to="/cate/1" :class="$style.navLink">
                前端
              </router-link>
            </li>
            <li :class="$style.nav">
              <router-link to="/cate/2" :class="$style.navLink">
                Rust
              </router-link>
            </li>
            <li :class="$style.nav">
              <router-link to="/about" :class="$style.navLink">
                关于MUAEN
              </router-link>
            </li>
            <li :class="$style.nav">
              <router-link to="/mall" :class="$style.navLink">
                谭小贱代购
              </router-link>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>

<style lang="scss" module>
.wrap {
  box-shadow: none;
  background-color: transparent;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 11;
  padding: 20px 0 0;
  height: 90px;
  transition: transform 300ms linear;
  :global(.container) {
    height: 100%;
  }
}
.navbar {
  display: flex;
  height: 100%;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
}
.brand {
  display: flex;
  text-decoration: none;
  color: #fff;
  align-items: center;
  /* prettier-ignore */
  width: 168PX;
  height: 100%;
  letter-spacing: 5px;
}
.collapse {
  height: 100%;
}
.navs {
  display: flex;
  flex-direction: row;
  height: 100%;
}
.nav {
  display: flex;
  align-items: center;
  :global(.router-link-active) {
    color: #fff;
    &::after {
      background: #fff;
      opacity: 1;
    }
  }
}
.navLink {
  display: flex;
  height: 100%;
  align-items: center;
  /* prettier-ignore */
  font-size: 14PX;
  text-decoration: none;
  color: #d4d4d4;
  margin-right: 20px;
  padding: 5px 5px 0;
  position: relative;
  &::after {
    content: "";
    position: absolute;
    margin: auto;
    bottom: 15px;
    width: 4px;
    height: 4px;
    left: 0;
    right: 0;
    opacity: 0;
    border-radius: 6px;
    background: #000;
    transition: all 0.3s ease 0s;
  }
}
@media (max-width: 768px) {
  .brand {
    /* prettier-ignore */
    width: 100PX;
  }
  .navLink::after {
    opacity: 0 !important;
  }
}
</style>
