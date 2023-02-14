<template>
  <div>
    <header class="pt-12 pb-9 sm:pb-16 sm:text-center">
      <h1 class="mb-2 text-8xl sm:text-4xl text-slate-800 font-extrabold dark:text-slate-100" style="letter-spacing:-1px;">
        Blog
        <span class="text-base text-slate-700 font-normal dark:text-slate-400">
          - all my study diary
        </span>
      </h1>
    </header>
    <div class="space-y-16 mx-auto max-w-5xl">
      <blog-item
        v-for="article in articles"
        :key="article.title"
        :title="article.title"
        :description="article.description"
        :date="article.date"
        :slug="article.slug"
      ></blog-item>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content("articles")
      .only([
        "title",
        "description",
        "img",
        "slug",
        "tag",
        "author",
        "date",
        "draft",
      ])
      .sortBy("date", "asc")
      .fetch();

    return {
      articles,
    };
  },
  head: {
    title: "blog | borigil blog",
    meta: [
      { charset: "utf-8" },
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        hid: "description",
        name: "description",
        content: "Its Borigil's Pen and Paper to write ",
      },
    ],
    link: [{ rel: "icon", type: "image/x-icon", href: "/favicon.ico" }],
  },
};
</script>

<style></style>
