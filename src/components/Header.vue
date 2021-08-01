<template>
  <header>
    <div class="nav nav-pills">
      <div
        v-for="nav in navigation"
        key="nav.name"
        class="nav-item">
        <RouterLink
          :to="nav.href"
          class="nav-link"
          aria-current="page">
          {{ nav.name }}
        </RouterLink>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      navigation: [
        {
          name: "HOME",
          href: "/"
        },
        {
          name: "Sign In",
          href: "/login"
        },
        {
          name: "Sign Up",
          href: "/sign-up"
        },
      ]
    }
  },
  name: "Header"
}
</script>

<style scoped>

</style>