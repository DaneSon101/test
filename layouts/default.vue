<script setup>
const user = useUser()
</script>

<template>
    <nav>
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/movies">Movies</NuxtLink>
      <NuxtLink to="https://secondhandcars.co.za">Link</NuxtLink>
      <NuxtLink v-if="!user.isLoggedIn" to="/login">Login</NuxtLink>
      <a href="#" v-else @click.prevent="user.logout">Logout</a>
    </nav>
    <slot></slot>
</template>
