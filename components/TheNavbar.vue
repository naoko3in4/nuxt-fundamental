<template>
  <nav class="nav">
    <div class="logo">
      <nuxt-link class="logo text-lg" :to="{name: 'index'}">
        Nuxt Fundamentals
      </nuxt-link>
      <span class="subheader">A Vue School Course</span>
    </div>
  </nav>
</template>

<script>
export default {

}
</script>

<style scoped>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 78px;
  font-weight: lighter;
  letter-spacing: 0.5px;
}

.nav .logo {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.nav .logo .subheader {
  opacity: 0.7;
  font-size: 0.9rem;
  color: white;
}

.nav .nav-content {
  font-size: 1rem;
}
</style>