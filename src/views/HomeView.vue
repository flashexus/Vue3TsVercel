<script setup lang="ts">
import { RouterLink } from "vue-router";

import TheWelcome from "../components/TheWelcome.vue";
import HelloWorld from "../components/HelloWorld.vue";

const items = [
  {
    title: "Home",
    path: "/",
  },
  {
    title: "About",
    path: "/about",
  },
  {
    title: "Article",
    path: "/articles",
  },
];
</script>

<template>
  <v-container>
    <v-row>
      <v-col cols="6">
        <header class="d-flex align-center flex-column">
          <img
            alt="Vue logo"
            class="logo"
            src="@/assets/logo.svg"
            width="125"
            height="125"
          />
          <div class="wrapper">
            <HelloWorld msg="Vue3 旅日記" />

            <nav>
              <span v-for="item in items" :key="item.title">
                <router-link :to="{ path: item.path }"
                  >{{ item.title }}
                </router-link>
              </span>
            </nav>
          </div>
        </header>
      </v-col>
      <v-col cols="6">
        <main>
          <TheWelcome />
        </main>
      </v-col>
    </v-row>
  </v-container>
</template>
<style scoped>
header {
  /* line-height: 1.5; */
  /* max-height: 100vh; */
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  /* width: 100%; */
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    /* display: flex;
    place-items: center; */
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    /* display: flex;
    place-items: flex-start;
    flex-wrap: wrap; */
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
