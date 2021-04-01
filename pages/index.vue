<template>
  <div>
    <section id="main" class="h-screen pt-24" style="background: #ffd02f">
      <LogoDisassemble class="mx-auto" width="50%"></LogoDisassemble>
    </section>
    <section class="h-screen" style="background: #fff">
      <!-- data-aos="fade-up" -->
      <!-- data-aos-delay="100" -->
      <div class="h-full">
        <h3 class="sm:pl-20 mt-10 text-4xl">Latest Projects</h3>
        <div>
          <div v-for="project of projects" :key="project.slug">
            <div class="my-5 mx-auto sm:grid grid-cols-2 lg:w-10/12">
              <div class="col-span-1 overflow-hidden">
                <!-- :src="require(`~/assets/resources/${project.img}`)" -->
                <img
                  src="https://images.unsplash.com/photo-1615130378909-21b80a796749?crop=entropy&cs=tinysrgb&fit=crop&fm=jpg&h=600&ixlib=rb-1.2.1&q=80&w=600"
                  :alt="project.img"
                  class="transition duration-500 ease-in-out transform hover:-translate-y-1 hover:scale-110 h-full w-full object-cover"
                />
              </div>
              <div
                class="pt-10 sm:pl-10 col-span-1 h-full"
                style="background-color: #f2eae2"
              >
                <nuxt-link
                  :to="{ name: 'posts-slug', params: { slug: project.slug } }"
                >
                  <div class="flex flex-col">
                    <h2
                      class="font-bold uppercase"
                      style="color: #3098f2; letter-spacing: 0.01em"
                    >
                      {{ project.client }}
                    </h2>
                    <p
                      class="mt-5 overflow-ellipsis overflow-hidden font-normal"
                      style="height: 45%; font-size: 32px"
                    >
                      {{ project.description.substring(0, 100) }}
                    </p>
                    <div class="mt-10 flex flex-row">
                      <svg
                        width="24"
                        height="25"
                        viewBox="0 0 24 25"
                        fill="none"
                      >
                        <g>
                          <circle
                            cx="12"
                            cy="12.5"
                            r="12"
                            fill="#3098F3"
                          ></circle>
                          <path
                            d="M10 8L14.5 12.5L10 17"
                            stroke="white"
                            stroke-width="2"
                            stroke-miterlimit="10"
                          ></path>
                        </g>
                        <defs>
                          <clipPath>
                            <rect
                              y="0.5"
                              width="24"
                              height="24"
                              fill="white"
                            ></rect>
                          </clipPath>
                        </defs>
                      </svg>
                      <span class="ml-3 font-medium">View Project Summary</span>
                    </div>
                  </div>
                </nuxt-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="h-screen" style="background: #fff"></section>
    <section class="h-screen" style="background: #fff">
      <h3 class="sm:pl-20 mt-10 text-4xl">Trusted By</h3>
      <div class="mx-16">
        <vue-horizontal-list :items="items" :options="options">
          <template v-slot:default="{ item }">
            <div class="px-5 py-3 flex flex-col justify-center items-center">
              <img class="tb-logo" :src="item.logo" alt="" />
              <h5 class="text-center text-gray-700">{{ item.comapany }}</h5>
            </div>
          </template>
        </vue-horizontal-list>
      </div>
    </section>
    <!-- <no-ssr>
      <vue-particles
        color="#140957"
        :particleOpacity="0.7"
        :particlesNumber="80"
        shapeType="circle"
        :particleSize="4"
        linesColor="#1EC2F2"
        :linesWidth="1"
        :lineLinked="true"
        :lineOpacity="0.4"
        :linesDistance="150"
        :moveSpeed="3"
        :hoverEffect="true"
        hoverMode="grab"
        :clickEffect="true"
        clickMode="push"
      >
      </vue-particles>
    </no-ssr> -->
  </div>
</template>

<script>
export default {
  updated() {
    document.querySelector(".vhl-navigation")?.remove();
    // document.querySelector(".vhl-btn-left")?.remove();
  },
  mounted() {
    document.querySelector(".vhl-navigation")?.remove();
    VANTA.TOPOLOGY({
      el: "#main",
      mouseControls: true,
      touchControls: true,
      gyroControls: false,
      minHeight: 200.0,
      minWidth: 200.0,
      scale: 1.0,
      scaleMobile: 1.0,
      color: 0xffffff,
      backgroundColor: 0xffd02f,
    });
  },
  data() {
    return {
      projects: [
        {
          slug: "",
          img: "",
          client: "ID Bank",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor",
        },
        {
          slug: "",
          img: "",
          client: "ID Bank",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor",
        },
      ],
      options: {
        autoplay: { play: true, repeat: true, speed: 3000 },
        responsive: [
          { end: 576, size: 1 },
          { start: 576, end: 768, size: 2 },
          { start: 768, end: 992, size: 3 },
          { size: 5 },
        ],
        list: {
          // 1200 because @media (min-width: 1200px) and therefore I want to switch to windowed mode
          windowed: 1200,

          // Because: #app {padding: 80px 24px;}
          padding: 24,
        },
      },
      items: [
        {
          comapany: "IDBank",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "IDBank",
          logo:
            "https://asue.am/images/1559729173/02a3067aad7848c7b4f64a7c.jpg",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
        {
          comapany: "Item 0",
          logo:
            "http://assets.stickpng.com/thumbs/58482acecef1014c0b5e4a1e.png",
        },
      ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=DM+Sans&display=swap");

/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.tb-logo {
  filter: grayscale(80%);
  width: 40%;
}

.tb-logo:hover {
  filter: grayscale(0%);
}
</style>
