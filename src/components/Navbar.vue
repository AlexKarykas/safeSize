<template>
  <b-navbar class="navbar--custom">
    <div v-b-toggle.sidebar class="d-block d-sm-none">
      <b-container>
        <b-row align-v="center">
          <b-icon icon="filter"></b-icon>
          <p class="navbar__text">FILTERS</p>
        </b-row>
      </b-container>
    </div>
    <div v-b-toggle.sidebar class="d-none d-sm-block">
      <b-img src="../../public/logo.png" alt="Logo" height="48px"></b-img>
    </div>

    <b-navbar-nav class="ml-auto">
      <b-container>
        <b-row align-v="center">
          <p class="navbar__text d-none d-sm-block">Aristotelis Michailidis</p>
          <b-avatar
            icon="basket"
            class="cart-avatar"
            variant="primary"
          ></b-avatar>
          <b-avatar
            class="name-avatar d-block d-sm-none"
            variant="light"
            text="AM"
          ></b-avatar>
          <b-avatar
            icon="chevron-down"
            class="chevron-avatar d-none d-sm-block"
            variant="primary"
          ></b-avatar>
        </b-row>
      </b-container>
    </b-navbar-nav>
  </b-navbar>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style lang="scss">
.navbar--custom {
  background: $white;
  border-radius: 0 0 15px 15px;
  box-shadow: $shadow-lg;
}

.navbar__text {
  margin-bottom: 0;
  margin-left: 0.6rem;
  font-weight: bold;
}

.name-avatar {
  box-shadow: $shadow;
  background-color: $white;
}

.cart-avatar {
  margin: 0 0.6rem;
  box-shadow: $shadow;
  background-color: $lightblue;
}

.chevron-avatar {
  margin: 0 0.6rem;
  padding-top: 0.5rem;
  box-shadow: $shadow;
  background-color: $lightblue;
}
</style>