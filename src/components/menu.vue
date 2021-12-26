<template>
  <div class="menu">
    <div class="menu-list">
      <div
        class="menu-list__link link"
        @click="
          modals.settings = true;
          closeMenu();
        "
      >
        <img src="icon/cog.svg" class="link__img" alt="" />
        <span class="link__title">Settings</span>
      </div>
      <div class="menu__separator"></div>
      <router-link
        to="/login"
        class="menu-list__link"
        @click.native="closeMenu()"
      >
        <img src="icon/log-out.svg" class="link__img" alt="" />
        <span class="link__title">Relogin</span>
      </router-link>
    </div>

    <ModalSupport
      v-model="modals.support"
      v-if="modals.support"
      @isSuccess="
        modals.support = false;
        modals.success = true;
      "
    />
    <ModalSuccess v-model="modals.success" v-if="modals.success" />
    <ModalSettings
      v-model="modals.settings"
      v-if="modals.settings"
      @isSuccess="
        modals.settings = false;
        modals.success = true;
      "
      @openSupport="
        modals.settings = false;
        modals.success = false;
        modals.support = true;
      "
    />
  </div>
</template>

<script>
import ModalSuccess from "./modal/modal-success";
import ModalSupport from "./modal/modal-support";
import ModalSettings from "./modal/modal-settings";

export default {
  name: "menu",
  components: { ModalSettings, ModalSupport, ModalSuccess },
  data() {
    return {
      modals: {
        settings: false,

        success: false,
        support: false,
      },
    };
  },
  methods: {
    closeMenu() {
      this.$emit("closeMenu");
    },
  },
};
</script>

<style lang="scss">
.menu-list {
  background: #14131e;
  border: 2px solid #28263a;
  border-radius: 10px;
  z-index: 10;
  width: 200px;
  padding: 10px 0;
  position: absolute;
  top: 70px;
  right: 0;

  &__link {
    display: flex;
    gap: 16px;
    padding: 14px 24px;
    align-items: center;
    justify-content: start;
    cursor: pointer;
  }
}

.link {
  &__title {
    font-family: LabGrotesque, serif;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    color: $color-white;

    &:hover {
      color: $color-primary;
    }
  }

  &__img {
    width: 20px;
  }
}

.menu__separator {
  width: 100%;
  height: 1px;
  background: #28263a;
}

.modal-enter-active,
.modal-leave-active {
  transition: opacity 1s;
}
.modal-enter,
.modal-leave-to {
  opacity: 0;
}
</style>
