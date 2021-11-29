<template>
  <div class="header">
    <img src="/icon/logo.svg" alt="logo" class="logo" />
    <nav class="nav">
      <router-link to="/" class="nav__item text-nav">Foil</router-link>
      <router-link to="/" class="nav__item text-nav">Learn</router-link>
      <router-link to="/" class="nav__item text-nav">Blog</router-link>
      <router-link to="/" class="nav__item text-nav">Product</router-link>
      <router-link to="/" class="nav__item text-nav">Community</router-link>
      <router-link to="/" class="nav__item text-nav"
        >Block Explorer
      </router-link>
      <router-link to="/" class="nav__item text-nav">Contact Us</router-link>
    </nav>
    <div class="action-block">
      <div class="action-block__icons">
        <img src="" alt="" />
        <img src="" alt="" />
        <img src="" alt="" />
      </div>
      <p class="action-block__language text-nav">EN</p>
      <div class="grad">
        <img src="/image/unnamed.jpg" alt="" class="user-icon" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "header",
};
</script>

<style lang="scss">
.header {
  position: fixed;
  background: rgba(0, 0, 0, 0.46);
  border-bottom: $color-white solid 1px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 5px 48px;
  width: 100vw;
  z-index: 10;
}

.text-nav {
  font-family: Axiforma, serif;
  font-size: 14px;
  font-style: normal;
  font-weight: normal;
  line-height: 22px;
  color: $color-nav-text;
  transition: all ease-in-out 0.3s;

  &:hover {
    color: $color-text-active;
    transition: all ease-in-out 0.3s;
  }

  &--active {
    color: $color-text-active;
  }
}

.nav {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 82px;
}

.action-block {
  display: flex;
  align-items: center;
  gap: 30px;
  &__icons {
  }
  &__language {
    cursor: pointer;
  }
}

.user-icon {
  color: #313149;
  display: inline-block;
  margin: 2px;
  width: 35px;
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
}
</style>
