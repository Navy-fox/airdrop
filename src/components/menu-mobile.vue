<template>
  <div class="menu-mobile">
    <img
      src="/icon/close.svg"
      class="menu-mobile__close"
      alt=""
      @click="closeMobMenu"
    />
    <nav class="menu-mobile__nav">
      <router-link
        class="menu-mobile__link"
        :to="i.to"
        v-for="(i, k) in links"
        :key="k"
      >
        {{ i.name }}
      </router-link>
      <router-link
        class="menu-mobile__link"
        to="/"
        @click.native="
          modals.settings = true;
          closeMobMenu();
        "
      >
        Settings
      </router-link>
      <router-link
        class="menu-mobile__link"
        to="/login"
        @click.native="closeMobMenu"
      >
        Relogin
      </router-link>
    </nav>
    <div class="menu-mobile__social">
      <img src="/icon/md.svg" alt="" class="menu-mobile__icon" />
      <img src="/icon/tw.svg" alt="" class="menu-mobile__icon" />
      <img src="/icon/tg.svg" alt="" class="menu-mobile__icon" />
    </div>

    <ModalSettings
      v-model="modals.settings"
      v-if="modals.settings"
      @isSuccess="
        modals.support = false;
        modals.success = true;
      "
      @openSupport="
        modals.settings = false;
        modals.success = false;
        modals.support = true;
      "
    />
    <ModalSupport
      v-model="modals.support"
      v-if="modals.support"
      @isSuccess="
        modals.support = false;
        modals.success = true;
      "
    />
    <ModalSuccess v-model="modals.success" v-if="modals.success" />
  </div>
</template>

<script>
import { LINKS_LIST } from "../data/LINKS_LIST";
import ModalSettings from "./modal/modal-settings";
import ModalSupport from "./modal/modal-support";
import ModalSuccess from "./modal/modal-success";

export default {
  name: "menu-mobile",
  components: { ModalSuccess, ModalSupport, ModalSettings },
  data() {
    return {
      links: LINKS_LIST,

      modals: {
        settings: false,
        success: false,
        support: false,
      },
    };
  },
  methods: {
    closeMobMenu() {
      this.$emit("closeMobMenu");
    },
  },
};
</script>

<style lang="scss">
.menu-mobile {
  width: 80%;
  height: 100%;
  position: fixed;
  top: 0;
  right: 0;
  padding: 60px 48px;

  background: #14131e;
  border-radius: 10px 0px 0px 10px;
  border-left: 2px solid #28263a;

  @include mob() {
    width: 100%;
    padding: 48px 24px;
  }

  &__close {
    position: absolute;
    right: 8px;
    top: 8px;
    width: 36px;
    height: 36px;
  }

  &__nav {
    display: flex;
    flex-direction: column;
  }

  &__link {
    font-family: adineuePROCyr, serif;
    font-style: normal;
    font-weight: bold;
    line-height: 105%;
    font-size: 20px;
    color: $color-white;
    cursor: pointer;

    &:after,
    &:before {
      content: "";
      display: block;
      margin: 15px 0;
      background: gradient-accent(-90deg, 10%, 70%);
      width: 100%;
      height: 1px;
      opacity: 0.5;
    }
  }

  &__social {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 80%;
    margin-left: auto;
    margin-right: auto;
    margin-top: 10px;
  }

  &__icon {
    cursor: pointer;
    width: 48px;
    height: 48px;
  }
}
</style>
