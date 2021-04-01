<template>
  <div>
    <Header />
    <Nuxt />
  </div>
</template>

<style>
html,
body {
  height: 100%;
  font-family: "DM Sans", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
}

body {
  background-color: #fff;
  overflow: overlay;
}
a {
  text-decoration: none;
}
/* total width */
body::-webkit-scrollbar {
  background-color: transparent;
}

::-webkit-scrollbar-thumb {
  box-shadow: inset 0 0 10px 10px rgba(128, 128, 128, 0.4);
  border-radius: 16px;
  border: solid 5px transparent;
}
</style>
