<template>
  <header id="nav" class="layout__header">
    <div class="header__left">
      <router-link class="header__name" to="/">Ognjen Pejović</router-link>
    </div>

    <div class="navigation__home">
      <router-link to="/" class="navigation__link">Home</router-link>
    </div>
    <div class="navigation__about">
      <router-link to="/about" class="navigation__link">About</router-link>
    </div>

    <button class="navigation__theme_toggler" @click="toggleTheme">
      <svg
        class="navigation__theme_toggler_icon"
        width="40"
        height="40"
        viewBox="0 0 40 40"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <rect
          x="0.75"
          y="0.75"
          width="38.5"
          height="38.5"
          rx="19.25"
          stroke="currentColor"
          stroke-width="1"
        />
        <path
          d="M27 12C26.4477 12 26 11.5523 26 11V11C26 10.45 25.55 10 25 10H13C12.45 10 12 10.45 12 11V15C12 15.55 12.45 16 13 16H25C25.55 16 26 15.55 26 15V14.5C26 14.2239 26.2239 14 26.5 14V14C26.7761 14 27 14.2239 27 14.5V16C27 17.1046 26.1046 18 25 18H22C19.2386 18 17 20.2386 17 23V29C17 29.55 17.45 30 18 30H20C20.55 30 21 29.55 21 29V24C21 21.7909 22.7909 20 25 20V20C27.2091 20 29 18.2091 29 16V13.5C29 12.6716 28.3284 12 27.5 12H27Z"
          fill="currentColor"
        />
      </svg>
    </button>
  </header>

  <main>
    <router-view v-slot="{ Component }">
      <transition name="fade" mode="out-in">
        <component :is="Component"></component>
      </transition>
    </router-view>
  </main>

  <footer class="layout__footer">
    <section class="footer__socials">
      <a href="https://github.com/opejovic">
        <svg
          fill="currentColor"
          height="24"
          aria-hidden="true"
          viewBox="0 0 16 16"
          version="1.1"
          width="24"
          data-view-component="true"
        >
          <path
            fill-rule="evenodd"
            d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"
          ></path>
        </svg>
      </a>

      <a href="https://www.linkedin.com/in/ognjen-pejovic-831a191b/"
        ><svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="currentColor"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M19 0L5 0C2.239 0 0 2.239 0 5L0 19C0 21.761 2.239 24 5 24H19C21.762 24 24 21.761 24 19V5C24 2.239 21.762 0 19 0ZM8 19H5V8H8V19ZM6.5 6.732C5.534 6.732 4.75 5.942 4.75 4.968C4.75 3.994 5.534 3.204 6.5 3.204C7.466 3.204 8.25 3.994 8.25 4.968C8.25 5.942 7.467 6.732 6.5 6.732ZM20 19H17V13.396C17 10.028 13 10.283 13 13.396V19H10V8H13V9.765C14.396 7.179 20 6.988 20 12.241V19Z"
            fill="currentColor"
          /></svg
      ></a>

      <a href="https://twitter.com/opejovic">
        <svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="currentColor"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g clip-path="url(#clip0_312:98)">
            <path
              d="M24 4.55699C23.117 4.94899 22.168 5.21299 21.172 5.33199C22.189 4.72299 22.97 3.75799 23.337 2.60799C22.386 3.17199 21.332 3.58199 20.21 3.80299C19.313 2.84599 18.032 2.24799 16.616 2.24799C13.437 2.24799 11.101 5.21399 11.819 8.29299C7.728 8.08799 4.1 6.12799 1.671 3.14899C0.381 5.36199 1.002 8.25699 3.194 9.72299C2.388 9.69699 1.628 9.47599 0.965 9.10699C0.911 11.388 2.546 13.522 4.914 13.997C4.221 14.185 3.462 14.229 2.69 14.081C3.316 16.037 5.134 17.46 7.29 17.5C5.22 19.123 2.612 19.848 0 19.54C2.179 20.937 4.768 21.752 7.548 21.752C16.69 21.752 21.855 14.031 21.543 7.10599C22.505 6.41099 23.34 5.54399 24 4.55699V4.55699Z"
              fill="currentColor"
            />
          </g>
          <defs>
            <clipPath id="clip0_312:98">
              <rect width="24" height="24" fill="white" />
            </clipPath>
          </defs>
        </svg>
      </a>

      <!-- Instagram -->
      <a href="" v-if="false">
        <svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="currentColor"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M12 2.163C15.204 2.163 15.584 2.175 16.85 2.233C20.102 2.381 21.621 3.924 21.769 7.152C21.827 8.417 21.838 8.797 21.838 12.001C21.838 15.206 21.826 15.585 21.769 16.85C21.62 20.075 20.105 21.621 16.85 21.769C15.584 21.827 15.206 21.839 12 21.839C8.796 21.839 8.416 21.827 7.151 21.769C3.891 21.62 2.38 20.07 2.232 16.849C2.174 15.584 2.162 15.205 2.162 12C2.162 8.796 2.175 8.417 2.232 7.151C2.381 3.924 3.896 2.38 7.151 2.232C8.417 2.175 8.796 2.163 12 2.163V2.163ZM12 0C8.741 0 8.333 0.014 7.053 0.072C2.695 0.272 0.273 2.69 0.073 7.052C0.014 8.333 0 8.741 0 12C0 15.259 0.014 15.668 0.072 16.948C0.272 21.306 2.69 23.728 7.052 23.928C8.333 23.986 8.741 24 12 24C15.259 24 15.668 23.986 16.948 23.928C21.302 23.728 23.73 21.31 23.927 16.948C23.986 15.668 24 15.259 24 12C24 8.741 23.986 8.333 23.928 7.053C23.732 2.699 21.311 0.273 16.949 0.073C15.668 0.014 15.259 0 12 0ZM12 5.838C11.1908 5.838 10.3895 5.99739 9.6419 6.30705C8.8943 6.61672 8.215 7.07061 7.64281 7.64281C7.07061 8.215 6.61672 8.8943 6.30705 9.6419C5.99738 10.3895 5.838 11.1908 5.838 12C5.838 12.8092 5.99738 13.6105 6.30705 14.3581C6.61672 15.1057 7.07061 15.785 7.64281 16.3572C8.215 16.9294 8.8943 17.3833 9.6419 17.6929C10.3895 18.0026 11.1908 18.162 12 18.162C13.6343 18.162 15.2016 17.5128 16.3572 16.3572C17.5128 15.2016 18.162 13.6343 18.162 12C18.162 10.3657 17.5128 8.79841 16.3572 7.64281C15.2016 6.48721 13.6343 5.838 12 5.838V5.838ZM12 16C10.9391 16 9.92172 15.5786 9.17157 14.8284C8.42143 14.0783 8 13.0609 8 12C8 10.9391 8.42143 9.92172 9.17157 9.17157C9.92172 8.42143 10.9391 8 12 8C13.0609 8 14.0783 8.42143 14.8284 9.17157C15.5786 9.92172 16 10.9391 16 12C16 13.0609 15.5786 14.0783 14.8284 14.8284C14.0783 15.5786 13.0609 16 12 16ZM18.406 4.155C18.2168 4.155 18.0295 4.19226 17.8547 4.26465C17.68 4.33704 17.5212 4.44315 17.3874 4.57691C17.2537 4.71068 17.1475 4.86947 17.0752 5.04424C17.0028 5.21901 16.9655 5.40633 16.9655 5.5955C16.9655 5.78467 17.0028 5.97199 17.0752 6.14676C17.1475 6.32153 17.2537 6.48032 17.3874 6.61409C17.5212 6.74785 17.68 6.85396 17.8547 6.92635C18.0295 6.99874 18.2168 7.036 18.406 7.036C18.788 7.036 19.1544 6.88423 19.4246 6.61409C19.6947 6.34394 19.8465 5.97754 19.8465 5.5955C19.8465 5.21346 19.6947 4.84706 19.4246 4.57691C19.1544 4.30677 18.788 4.155 18.406 4.155V4.155Z"
            fill="currentColor"
          />
        </svg>
      </a>

      <!-- Youtube -->
      <a href="" v-if="false">
        <svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="currentColor"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M19.615 3.18413C16.011 2.93813 7.984 2.93913 4.385 3.18413C0.488 3.45013 0.029 5.80412 0 12.0001C0.029 18.1851 0.484 20.5491 4.385 20.8161C7.985 21.0611 16.011 21.0621 19.615 20.8161C23.512 20.5501 23.971 18.1961 24 12.0001C23.971 5.81512 23.516 3.45113 19.615 3.18413V3.18413ZM9 16.0001V8.00013L17 11.9931L9 16.0001Z"
            fill="currentColor"
          />
        </svg>
      </a>
    </section>
    <section class="footer__email">
      <a href="mailto:ognjen@fullstacked.dev" class="email__link"
        >ognjen@fullstacked.dev</a
      >
    </section>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      theme: localStorage.getItem("theme"),
    };
  },

  created() {
    try {
      // Checks for the color scheme of the device.
      // In this case it checks for anything that is not light theme.
      var media = window.matchMedia(
          "not all and (prefers-color-scheme: light)"
        ),
        body = document.body;
      if (localStorage.getItem("theme") == "dark") {
        body.setAttribute("data-theme", "dark");
      } else if (localStorage.getItem("theme") == "light") {
        body.setAttribute("data-theme", "light");
      } else if (media.matches) {
        body.setAttribute("data-theme", "dark");
        localStorage.setItem("theme", "dark");
      }
      media.addListener(function () {
        if (media.matches) {
          body.setAttribute("data-theme", "dark");
          localStorage.setItem("theme", "dark");
        } else {
          body.setAttribute("data-theme", "light");
          localStorage.setItem("theme", "light");
        }
      });
    } catch (err) {
      console.log(err);
    }
  },

  methods: {
    toggleTheme() {
      document.body.classList.add("color-transition");
      if (this.theme === "dark") {
        this.theme = "light";
        document.body.setAttribute("data-theme", "light");
        localStorage.setItem("theme", "light");
      } else {
        this.theme = "dark";
        document.body.setAttribute("data-theme", "dark");
        localStorage.setItem("theme", "dark");
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 200ms ease-in-out;
}
.fade-enter-from,
.fade-leave-active {
  opacity: 0;
}
</style>
