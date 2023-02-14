<template>
  <nav class="md:max-w-5xl mx-auto sticky top-0 z-50 max-w-screen-lg mx-auto">
    <div class="bg-white flex flex-wrap items-center justify-end px-10 md:py-0 py-2 overflow-hidden border-b border-gray-200 font-2xl sm:px-4 md:overflow-visible md:px-2">
      <input class="menu-btn hidden" type="checkbox" id="menu-btn" />
      <label class="menu-icon block cursor-pointer md:hidden px-2 relative select-none" for="menu-btn">
        <span class="bg-grey-darkest flex items-center relative"></span>
      </label>

      <ul class="flex justify-center list-reset m-0 w-full md:w-auto">
        <li v-for="item in navLinks" :key="item.path">
          <NuxtLink
            :to="item.path"
            class="block md:inline-block px-2 py-3 no-underline text-grey-darkest hover:text-grey-darker font-midium text-lg md:text-base"
          >
            {{ item.name }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
import menu from "../data/menu";

export default {
  name: "TheHeader",
  data() {
    return {
      navLinks: menu,
    };
  },
};
</script>

<style>
.nuxt-link-exact-active {
  @apply text-indigo-600;
}
</style>
