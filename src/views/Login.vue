<template>
  <section class="max-w-2xl mx-auto rounded bg-content-800">
    <div class="container flex items-center justify-center text-center">
      <form
        @submit.prevent
        class="flex flex-col w-full max-w-xl p-12 rounded shadow-lg"
      >
        <label
          for="username"
          class="self-start text-xs font-semibold text-content-200"
          >Username or Email</label
        >
        <input
          id="username"
          type="text"
          class="flex items-center h-12 px-4 mt-2 bg-gray-200 rounded focus:outline-none focus:ring-2"
        />
        <label
          for="password"
          class="self-start mt-3 text-xs font-semibold text-content-200"
          >Password</label
        >
        <input
          id="password"
          type="password"
          class="flex items-center h-12 px-4 mt-2 bg-gray-200 rounded focus:outline-none focus:ring-2"
        />
        <button @click="login" class="btn btn-primary mt-4">Login</button>
      </form>
    </div>
  </section>
</template>

<script setup>
import { useRouter } from 'vue-router'
import { isAuthenticated } from '../helpers/useAuth'
const router = useRouter()
const login = () => {
  isAuthenticated.value = true
  router.push('/')
}
</script>
