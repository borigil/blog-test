<template>
  <div class="mt-12">
    <div class="mt-2">
      <h2 class="mb-2 text-xl text-gray-700 font-bold dark:text-blue-200 capitalize">
        Frontend
      </h2>

      <ul class="flex flex-wrap gap-4 items-center">
        <li class="flex items-center">
          <Html class="h-6 w-6 rounded-sm drop-shadow-sm"></Html>
        </li>
        <li class="flex items-center">
          <Css class="h-6 w-6 rounded-sm drop-shadow-sm"></Css>
        </li>
        <!-- <li class="flex items-center">
          <Bootstrap class="h-6 w-6"></Bootstrap>
        </li>
        <li class="flex items-center">
          <TailwindCss class="h-6 w-6"></TailwindCss>
        </li> -->
        <li class="flex items-center">
          <Javascript class="h-6 w-6"></Javascript>
        </li>
        <li class="flex items-center">
          <Vuejs class="h-6 w-6"></Vuejs>
        </li>
        <li class="flex items-center">
          <Nuxt class="h-6 w-6"></Nuxt>
        </li>
      </ul>
    </div>
    <!-- <div class="mt-4">
      <h2 class="mb-2 text-xl text-gray-700 font-bold dark:text-blue-200 capitalize">
        Backend
      </h2>
      <ul class="mb-6 flex flex-wrap gap-4">
        <li class="flex items-center">
          <Laravel class="h-6 w-6"></Laravel>
        </li>
        <li class="flex items-center">
          <Node class="h-6 w-6"></Node>
        </li>
      </ul>
    </div> -->
  </div>
</template>

<script>
import Javascript from "../assets/devicon/javascript.svg?inline";
import Html from "../assets/devicon/html.svg?inline";
import Css from "../assets/devicon/css.svg?inline";
import Vuejs from "../assets/devicon/vuejs.svg?inline";
import TailwindCss from "../assets/devicon/tailwindcss.svg?inline";
import Nuxt from "../assets/devicon/nuxt.svg?inline";
import Bootstrap from "../assets/devicon/bootstrap.svg?inline";
import Laravel from "../assets/devicon/laravel.svg?inline";
import Node from "../assets/devicon/node.svg?inline";
export default {
  components: {
    Javascript,
    Html,
    Css,
    Bootstrap,
    Vuejs,
    TailwindCss,
    Nuxt,
    Laravel,
    Node,
  },
};
</script>
