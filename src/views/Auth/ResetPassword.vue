<template>
  <FullScreenLayout>
    <div class="relative p-6 bg-white z-1 dark:bg-gray-900 sm:p-0">
      <div
        class="relative flex flex-col justify-center w-full h-screen lg:flex-row dark:bg-gray-900"
      >
        <div class="flex flex-col flex-1 w-full lg:w-1/2">
          <div class="w-full max-w-md pt-10 mx-auto">
            <router-link
              to="/"
              class="inline-flex items-center text-sm text-gray-500 transition-colors hover:text-gray-700 dark:text-gray-400 dark:hover:text-gray-300"
            >
              <svg
                class="stroke-current"
                xmlns="http://www.w3.org/2000/svg"
                width="20"
                height="20"
                viewBox="0 0 20 20"
                fill="none"
              >
                <path
                  d="M12.7083 5L7.5 10.2083L12.7083 15.4167"
                  stroke=""
                  stroke-width="1.5"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
              Back to dashboard
            </router-link>
          </div>
          <!-- Form -->
          <div class="flex flex-col justify-center flex-1 w-full max-w-md mx-auto">
            <div class="mb-5 sm:mb-8">
              <h1
                class="mb-2 font-semibold text-gray-800 text-title-sm dark:text-white/90 sm:text-title-md"
              >
                Reset Password
              </h1>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                Enter your email address and we will send you a link to reset your password.
Please check your inbox after submitting the form.
              </p>
              <span class="text-sm text-gray-500 dark:text-gray-400 mt-2 block">
                <b>Note:</b> If you don’t see the email, check your spam folder or try again later.
              </span>
            </div>
            <div>
              <form @submit.prevent="handleSubmit">
                <div class="space-y-5">
                  <!-- Password -->
                  <div>
                    <label
                      for="password"
                      class="mb-1.5 block text-sm font-medium text-gray-700 dark:text-gray-400"
                    >
                      Email<span class="text-error-500">*</span>
                    </label>
                    <div class="relative">
                      <input
                        v-model="email"
                        type="email"
                        id="email"
                        placeholder="Enter your email"
                        class="dark:bg-dark-900 h-11 w-full rounded-lg border border-gray-300 bg-transparent py-2.5 pl-4 pr-11 text-sm text-gray-800 shadow-theme-xs placeholder:text-gray-400 focus:border-brand-300 focus:outline-hidden focus:ring-3 focus:ring-brand-500/10 dark:border-gray-700 dark:bg-gray-900 dark:text-white/90 dark:placeholder:text-white/30 dark:focus:border-brand-800"
                      />
                    </div>
                  </div>
                  <!-- Checkbox -->
                  <div>
                    <button
                      type="submit"
                      class="flex items-center justify-center w-full px-4 py-3 text-sm font-medium text-white transition rounded-lg bg-brand-500 shadow-theme-xs hover:bg-brand-600"
                    >
                      Reset password
                    </button>
                  </div>
                </div>
              </form>
              <div class="mt-5">
                <p
                  class="text-sm font-normal text-center text-gray-700 dark:text-gray-400 sm:text-start"
                >
                  Already have an account?
                  <router-link
                    to="/signin"
                    class="text-brand-500 hover:text-brand-600 dark:text-brand-400"
                    >Sign In</router-link
                  >
                </p>
              </div>
            </div>
          </div>
        </div>
        <div
          class="relative items-center hidden w-full h-full lg:w-1/2 bg-brand-950 dark:bg-white/5 lg:grid"
        >
          <div class="flex items-center justify-center z-1">
            <common-grid-shape />
            <div class="flex flex-col items-center max-w-xs">
              <router-link to="/" class="block mb-4">
                <h2 class="text-xl md:text-2xl lg:text-4xl font-semibold text-white/90">MiniPay</h2>
              </router-link>
              <p class="text-center text-gray-400 dark:text-white/60">
                Your All-in-One Digital Wallet
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </FullScreenLayout>
</template>

<script setup lang="ts">
import FullScreenLayout from '@/components/layout/FullScreenLayout.vue'
import CommonGridShape from '@/components/common/CommonGridShape.vue'
import { ref } from 'vue'
import { RouterLink } from 'vue-router'

const firstName = ref('')
const lastName = ref('')
const email = ref('')
const password = ref('')
const showPassword = ref(false)
const agreeToTerms = ref(false)

const togglePasswordVisibility = () => {
  showPassword.value = !showPassword.value
}

const handleSubmit = () => {
  // Implement form submission logic here
  console.log('Form submitted', {
    firstName: firstName.value,
    lastName: lastName.value,
    email: email.value,
    password: password.value,
    agreeToTerms: agreeToTerms.value,
  })
}
</script>
