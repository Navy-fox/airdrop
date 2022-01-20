<template>
  <div class="header">
    <img src="icon/logo.svg" alt="logo" class="logo" />
    <nav class="nav">
      <router-link
        :to="i.to"
        class="nav__item text-nav"
        v-for="(i, k) in links"
        :key="k"
      >
        {{ i.name }}
      </router-link>
    </nav>
    <div class="action-block">
      <div class="action-block__icons">
        <img src="icon/md.svg" alt="" />
        <img src="icon/tg.svg" alt="" />
        <img src="icon/tw.svg" alt="" />
      </div>
      <p class="action-block__language text-nav">EN</p>
      <div class="grad">
        <transition name="menu">
          <Menu v-show="menuIsOpen" @closeMenu="menuIsOpen = false" />
        </transition>
        <img
          src="image/unnamed.jpg"
          alt=""
          class="user-icon"
          @click="menuIsOpen = !menuIsOpen"
        />
      </div>
      <transition name="menu-mobile">
        <MenuMobile
          v-show="menuMobIsOpen"
          @closeMobMenu="menuMobIsOpen = false"
        />
      </transition>

      <img
        src="icon/bar.svg"
        alt=""
        class="action-block__bar"
        @click="menuMobIsOpen = true"
      />
    </div>
  </div>
</template>

<script>
import Menu from "./menu";
import MenuMobile from "./menu-mobile";
import { LINKS_LIST } from "../data/LINKS_LIST";

export default {
  name: "header",
  components: { MenuMobile, Menu },
  data() {
    return {
      menuIsOpen: false,
      menuMobIsOpen: false,
      links: LINKS_LIST,
    };
  },
};
</script>

<style lang="scss">
.menu-mobile-enter-active,
.menu-mobile-leave-active {
  transition: right 1s;
}
.menu-mobile-enter,
.menu-mobile-leave-to {
  right: -80%;
}

.menu-enter-active,
.menu-leave-active {
  transition: opacity 1s;
}
.menu-enter,
.menu-leave-to {
  opacity: 0;
}

.header {
  position: fixed;
  background: rgba(10, 9, 20, 0.5);
  border-bottom: $color-white solid 1px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 5px 48px;
  width: 100vw;
  z-index: 10;
  @include lap() {
    padding: 5px 15px;
  }
  @include tab() {
    padding: 20px 15px;
  }
}

.text-nav {
  font-family: Axiforma, serif;
  font-size: 14px;
  font-style: normal;
  font-weight: normal;
  line-height: 22px;
  color: $color-nav-text;
  transition: all ease-in-out 0.3s;
  white-space: nowrap;

  &:hover {
    color: $color-text-active;
    transition: all ease-in-out 0.3s;
  }

  &--active {
    color: $color-text-active;
  }

  @include lap() {
    padding: 5px 3px;
  }
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  padding: 0 70px;
  flex-wrap: wrap;
  /*justify-content: center;*/
  /*gap: 82px;*/
  @include tab() {
    display: none;
  }
}

.action-block {
  display: flex;
  align-items: center;
  min-width: 220px;
  gap: 30px;

  &__icons {
    display: flex;
    flex-direction: row;
    gap: 5px;
    cursor: pointer;

    @include tab() {
      display: none;
    }
  }

  &__language {
    cursor: pointer;
  }

  &__bar {
    display: none;
    @include tab() {
      display: block;
      cursor: pointer;
    }
  }

  @include tab() {
    min-width: auto;
  }
}

.user-icon {
  color: #313149;
  display: inline-block;
  margin: 2px;
  min-width: 35px;
  height: 35px;
  border-radius: 50%;
  cursor: pointer;
}

.grad {
  --b: 5px; /* border width*/

  color: #e40ecf;
  display: inline-block;
  margin: 10px;
  width: 39px;
  height: 39px;
  position: relative;

  &:before {
    content: "";
    position: absolute;
    z-index: -1;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: linear-gradient(-135deg, #21d4fd 22%, #e40ecf 70%);
    border-radius: 50%;
  }
  @include tab() {
    display: none;
  }
}
</style>
