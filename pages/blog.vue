<template>
  <div>
    <h1 class="text-center">Latest Posts</h1>
    <div>
      <div v-for="article of articles" :key="article.slug">
        <div
          class="mb-3 mx-auto p-2 sm:p-4 sm:grid grid-cols-6 bg-white lg:col-span-2 lg:max-w-2xl lg:h-64"
          data-aos="fade-up"
          data-aos-delay="100"
        >
          <div class="col-span-2">
            <img
              :src="require(`~/assets/resources/${article.img}`)"
              :alt="article.img"
              class="rounded-lg"
            />
          </div>
          <div class="pt-5 sm:pt-0 sm:pl-10 col-span-4 h-full">
            <nuxt-link
              :to="{ name: 'posts-slug', params: { slug: article.slug } }"
            >
              <div class="flex flex-col h-full">
                <h2 class="text-2xl font-bold">
                  {{ article.title }}
                </h2>
                <p
                  class="text-gray-600 inline-block pt-2 overflow-ellipsis overflow-hidden"
                  style="height: 45%"
                >
                  {{ article.description.substring(0, 100) }}
                </p>
                <div class="mt-5 sm:mt-0 grid grid-cols-7">
                  <img
                    class="inline object-cover w-10 h-10 rounded-full col-span-1 mt-1"
                    src="https://images.pexels.com/photos/2589653/pexels-photo-2589653.jpeg?auto=compress&cs=tinysrgb&h=650&w=940"
                    alt="Profile image"
                  />
                  <div class="col-span-4">
                    <div class="font-semibold text-sm">
                      {{ article.author }}
                    </div>
                    <div class="text-sm text-gray-600">
                      {{ new Date(article.createdAt).toDateString() }}
                    </div>
                  </div>
                </div>
                <div class="mt-2">
                  <span
                    v-for="tag in getTags(article.tags)"
                    :key="tag"
                    class="text-sm text-blue-400 hover:text-blue-600"
                  >
                    {{ tag }}
                  </span>
                </div>
              </div>
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    getTags(rawTags) {
      return rawTags?.split(" ").map((x) => "#" + x);
    },
  },
  async asyncData({ $content, params }) {
    const articlesCount = (
      await $content("posts", params.slug).sortBy("createdAt", "asc").fetch()
    ).length;

    const articles = await $content("posts", params.slug)
      .only([
        "title",
        "description",
        "img",
        "author",
        "slug",
        "tags",
        "createdAt",
      ])
      .sortBy("createdAt", "asc")
      .limit(5)
      .fetch();

    return { articles };
  },
};
</script>

<style>
</style>