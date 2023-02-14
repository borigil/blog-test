<template>
  <div class="max-w-3xl px-4 mx-auto sm:px-6 xl:max-w-5xl xl:px-0">
    <div class="pt-12 pb-9 sm:pb-16 sm:text-center">
      <h1 class="mb-2 text-8xl sm:text-4xl text-slate-800 font-extrabold dark:text-slate-100" style="letter-spacing:-1px;">
        Project
        <span class="text-base text-slate-700 font-normal dark:text-slate-400">
          - my projects
        </span>
      </h1>
    </div>
    <main class="relative mb-auto">
      <div class="">
        <div class="container py-12">
          <div class="flex flex-wrap -m-4">
            <project-card
              v-for="item in projectsData"
              :key="item.title"
              :title="item.title"
              :description="item.description"
              :href="item.href"
              :github="item.github"
              :tech1="item.tech1"
              :tech2="item.tech2"
              :tech3="item.tech3"
            ></project-card>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import projectsData from "../data/projects";
export default {
  data() {
    return {
      projectsData: projectsData,
    };
  },
  head: {
    title: "projects | borigil blog",
    meta: [
      { charset: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        hid: "description",
        name: "description",
        content: "my project",
      },
    ],
    link: [{ rel: "icon", type: "image/x-icon", href: "/favicon.ico" }],
  },
};
</script>
