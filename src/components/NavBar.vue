<template>
  <div class="navbar mb-2 shadow-lg bg-content-800 text-content-100">
    <div class="flex-1 px-2 mx-2">
      <span class="text-lg font-bold"> LoginExample </span>
    </div>
    <div class="flex-none flex px-2 mx-2">
      <div class="flex">
        <router-link
          to="/"
          class="btn btn-ghost btn-sm rounded-btn hover:text-content-100"
        >
          Home
        </router-link>
        <router-link
          v-if="!isAuthenticated"
          to="/login"
          class="btn btn-ghost btn-sm rounded-btn hover:text-content-100"
        >
          Login
        </router-link>
        <div v-else>
          <router-link
            to="/secret"
            class="btn btn-ghost btn-sm rounded-btn hover:text-content-100"
          >
            Secret Page
          </router-link>
          <button
            class="btn btn-error btn-sm rounded-btn hover:text-content-100"
            @click="logout"
          >
            Logout
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useRouter } from 'vue-router'
import { isAuthenticated } from '../helpers/useAuth.js'
const router = useRouter()
const logout = () => {
  isAuthenticated.value = false
  router.push('/')
}
</script>
