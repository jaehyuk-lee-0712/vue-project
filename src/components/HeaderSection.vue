<script setup>
import { haederNav } from '@/constants';
</script>

<template>
  <header id="header" role="banner">
    <div class="header__innter">
      <h1 class="header__logo"><a href="#">PORTPORIO</a> <em>Vue.js</em></h1>
      <nav
        role="navigation"
        aria-label="메인 메뉴"
        class="header__nav"
        :class="{ show: inNavVisible }"
      >
        <ul>
          <li v-for="(nav, key) in haederNav" :key="key">
            <a :href="nav.url" @click="scrollLink($event)">{{ nav.title }}</a>
          </li>
        </ul>
      </nav>
      <div
        role="button"
        tabindex="0"
        aria-label="모바일 메인 메뉴"
        id="header-Toggle"
        class="header__nav__mobile"
        aria-expanded="false"
        @click="toggleMobileMenu"
      >
        <span></span>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      inNavVisible: false
    };
  },
  methods: {
    toggleMobileMenu() {
      this.inNavVisible = !this.inNavVisible;
    },
    scrollLink(event) {
      event.preventDefault();
      const targetId = event.target.getAttribute('href');
      const targetEl = document.querySelector(targetId);

      if (targetEl) {
        targetEl.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
};
</script>

<style lang="scss">
@import '@/assets/sass/mixin';

#header {
  @include position-fixed;

  .header__innter {
    @include flex-between;
    background-color: rgba(116, 99, 99, 0.1);
    backdrop-filter: blur(15px);

    .header__logo {
      font-size: 0.9rem;
      text-align: center;
      text-transform: uppercase;
      line-height: 1;

      em {
        font-size: 10px;
        display: block;
        color: var(--black200);
      }
    }

    .header__nav {
      @media (max-width: 800px) {
        display: none;

        &.show {
          display: block;

          ul {
            display: block;
            position: absolute;
            right: 0;
            top: 6px;
            background-color: rgba(116, 99, 99, 0.1);
            backdrop-filter: blur(15px);
            z-index: 10000;
            padding: 20px 0;

            li {
              display: block;
              text-align: right;

              a {
                display: inline-block;
                padding: 10px;
              }
            }
          }
        }

        &.show + .header__nav__mobile span ::before {
          width: 20px;
        }

        &.show + .header__nav__mobile span ::after {
          width: 20px;
        }
      }

      li {
        display: inline;

        a {
          text-transform: uppercase;
          font-size: 1rem;
          padding: 14px;
          position: relative;
          font-weight: 400;

          &::before {
            content: '';
            height: 1px;
            width: calc(100% - 8px);
            background-color: var(--black);
            left: 14px;
            position: absolute;
            bottom: 10px;
            transform: scaleX(0);
            transition: all 0.3s;
            color: var(--black200);

            &:hover::before {
              transform: scaleX(1);
            }
          }
        }
      }
    }

    .header__nav__mobile {
      width: 40px;
      height: 40px;
      cursor: pointer;
      display: none;

      @media (max-width: 800px) {
        display: block;
      }

      span {
        display: block;
        width: 40px;
        height: 2px;
        background-color: var(--black);
        margin-top: 19px;

        &::before {
          content: '';
          width: 40px;
          height: 2px;
          background: var(--black);
          position: absolute;
          right: 0;
          top: 6px;
          transition: width 0.3s;
        }
        &::after {
          content: '';
          width: 40px;
          height: 2px;
          background: var(--black);
          position: absolute;
          right: 0;
          bottom: 6px;
          transition: width 0.3s;
        }
      }
    }
  }
}
</style>
