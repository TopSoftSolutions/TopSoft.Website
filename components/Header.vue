<template>
  <header
    class="fixed top-0 w-full z-50 bg-transparent"
    style="transition: all 0.3s ease 0s;"
  >
    <nav>
      <div
        class="grid grid-cols-2 sm:grid-cols-3 px-8 sm:px-20"
        :class="prevScrollpos < 10 ? 'py-3' : 'py-3'"
      >
        <Logo width="3em" class="col-span-1 my-auto sm:mx-auto" />
        <div class="col-span-1 sm:hidden flex flex-row justify-end">
          <button
            @click="mobileMenuOpen = !mobileMenuOpen"
            class="w-10 h-10 text-gray-600 my-auto"
          >
            <svg
              fill="white"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
                clip-rule="evenodd"
              ></path>
            </svg>
          </button>
        </div>

        <div class="col-span-2" :class="{ hidden: !mobileMenuOpen }">
          <div
            class="flex flex-col sm:flex-row align-middle justify-center font-medium"
            style="font-size: 20px"
          >
            <nuxt-link class="text-black text-center p-5" to="/">
              Home
            </nuxt-link>
            <nuxt-link class="text-black text-center p-5" to="/blog">
              Blog
            </nuxt-link>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  data: function () {
    return {
      mobileMenuOpen: true,
      prevScrollpos: 0,
    };
  },
  beforeMount() {
    this.mobileMenuOpen = true && window.innerWidth > 640;
  },
  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.onScroll);
  },
  methods: {
    onScroll(e) {
      if (this.prevScrollpos === 0) {
        this.prevScrollpos = window.pageYOffset;
      }

      let currentScrollPos = window.pageYOffset;

      if (this.prevScrollpos > currentScrollPos) {
        document.querySelector("header").style.top = "0";
      } else {
        document.querySelector("header").style.top = "-100%";
      }
      this.prevScrollpos = currentScrollPos;
    },
  }
};
</script>

<style>
</style>
