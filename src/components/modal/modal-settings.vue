<template>
  <ModalWrapper>
    <form class="modal-settings form-wrapper">
      <img
        src="icon/close.svg"
        class="modal-close"
        alt=""
        @click="CloseModal"
      />
      <h3 class="form-wrapper__title heading heading--h3">Settings profile</h3>
      <div class="fieldset">
        <label class="fieldset__label">Your name</label>
        <input type="text" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">Your city</label>
        <input type="text" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">Phone number</label>
        <input type="tel" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">E-mail</label>
        <input type="email" class="fieldset__input" />
      </div>
      <div class="fieldset">
        <label class="fieldset__label">Wallet Foil</label>
        <input type="text" class="fieldset__input" />
      </div>
      <div class="collaboration">
        <div class="fieldset">
          <label class="fieldset__label">Google</label>
          <button
            type="button"
            class="fieldset__button"
            :class="{ 'fileset__button--joined': isJoined.google }"
            @click="isJoined.google = !isJoined.google"
          >
            {{ isJoined.google ? "Joined" : "Nickname" }}
          </button>
        </div>
        <div class="fieldset">
          <label class="fieldset__label">Telegram</label>
          <button
            type="button"
            class="fieldset__button"
            :class="{ 'fileset__button--joined': isJoined.telegram }"
            @click="isJoined.telegram = !isJoined.telegram"
          >
            {{ isJoined.telegram ? "Joined" : "@nickname" }}
          </button>
        </div>
        <div class="fieldset">
          <label class="fieldset__label">Facebook</label>
          <button
            type="button"
            class="fieldset__button"
            :class="{ 'fileset__button--joined': isJoined.facebook }"
            @click="isJoined.facebook = !isJoined.facebook"
          >
            {{ isJoined.facebook ? "Joined" : "@nickname" }}
          </button>
        </div>
        <div class="fieldset">
          <label class="fieldset__label">Linkedin</label>
          <button
            type="button"
            class="fieldset__button"
            :class="{ 'fileset__button--joined': isJoined.linkedin }"
            @click="isJoined.linkedin = !isJoined.linkedin"
          >
            {{ isJoined.linkedin ? "Joined" : "nickname" }}
          </button>
        </div>
      </div>
      <div class="separator"></div>
      <button type="button" class="button button--gradient" @click="isSuccess">
        Save settings
      </button>
      <div class="button-wrap" @click="openSupport">
        <button type="button" class="button button--grad-border">
          Support
        </button>
      </div>
      <button type="reset" class="button button--border">Cancel</button>
    </form>
  </ModalWrapper>
</template>

<script>
import ModalWrapper from "./modal-wrapper";
import ModalMixin from "../../mixins/modal-mixin";

export default {
  name: "modal-settings",
  components: { ModalWrapper },
  mixins: [ModalMixin],
  data() {
    return {
      isJoined: {
        google: true,
        telegram: true,
        facebook: true,
        linkedin: true,
      },
      modalSupport: false,
    };
  },
  methods: {
    openSupport() {
      this.$emit("openSupport");
    },
    isSuccess() {
      this.$emit("isSuccess");
    },
  },
  mounted() {
    document.querySelector("body").style.overflow = "hidden";
  },
  destroyed() {
    document.querySelector("body").style.overflow = "auto";
  },
};
</script>

<style lang="scss">
.collaboration {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-column: span 3;
  gap: 10px;

  .fieldset {
    grid-column: span 1;
  }
}

.separator {
  grid-column: span 3;
  width: 100%;
  height: 1px;
  background: #257b8e;
  margin: 20px 0;
}
</style>
