<template>
  <div class="md:fixed">
    <div class="md:block flex justify-center items-center">
      <nuxt-img
        :src="siteMetadata.author_image"
        loading="lazy"
        alt="me"
        class="shadow-xl md:h-32 md:w-32 h-20 w-20 rounded-full mx-7"
      />
      <div class="mb-2 mx-7 mt-6 justify-center items-center">
        <h1
          class="md:text-2xl text-xl text-gray-800 font-bold dark:text-blue-100"
        >
          {{ siteMetadata.author }}
        </h1>
        <div class="md:text-bace text-gray-600 dark:text-blue-100">
          {{ siteMetadata.position }}
        </div>
        <a
          :href="`mailto:${siteMetadata.email}`"
          class="text-gray-600 md:hidden mt-1 dark:text-blue-100"
        >
          {{ siteMetadata.email }}
        </a>
      </div>
    </div>

    <div class="mx-6 my-12 hidden md:block">
      <div class="my-2 text-gray-600 flex dark:text-blue-100 text-sm">
        <Mail />
        <a :href="`mailto:${siteMetadata.email}`" style="margin:2px;"> {{ siteMetadata.email }}</a>
      </div>
      <div class="my-2 text-gray-600 flex dark:text-blue-100 text-sm">
        <Glob />
        <p style="margin:2px;">{{ siteMetadata.location }}</p>
      </div>
      <div class="my-2 text-gray-600 flex dark:text-blue-200 text-sm">
        <Github />
        <a :href="siteMetadata.github" style="margin:2px;"> {{ siteMetadata.githubUser }}</a>
      </div>
    </div>
  </div>
</template>

<script>
import Mail from "../assets/icon/mail.svg?inline";
import Glob from "../assets/icon/glob.svg?inline";
import Github from "../assets/icon/github_new.svg?inline";
import siteMetaInfo from "@/data/sitemetainfo";
export default {
  components: { Mail, Glob, Github },
  data: () => {
    return {
      siteMetadata: siteMetaInfo,
    };
  },
};
</script>
