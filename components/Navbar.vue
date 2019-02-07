<template>
  <header>
    <div class="siteName">
      <a href="/">
        <h1>Kim Thompson</h1>
      </a>
    </div>
    <nav>
      <a href="#about">
        <div class="navlink">
          <fa :icon="faInfo"/>
          <span>About</span>
        </div>
      </a>
      <a href="#skills">
        <div class="navlink">
          <fa :icon="faCode"/>
          <span>Skills</span>
        </div>
      </a>
      <a href="https://medium.com/kim-thompson">
        <div class="navlink">
          <fa :icon="faRss"/>
          <span>Blog</span>
        </div>
      </a>
    </nav>
  </header>
</template>

<script>
import { faInfo, faCode, faRss } from '@fortawesome/free-solid-svg-icons'

export default {
  computed: {
    faInfo() {
      return faInfo
    },
    faCode() {
      return faCode
    },
    faRss() {
      return faRss
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../assets/scss/_vars.scss';
@import '../assets/scss/_mixins.scss';

a {
  transition: color 0.5s ease;
  color: $gallery;
  text-decoration: none;

  &:hover {
    color: $golden-fizz;
  }
}

@media (min-width: $phablet) {
  header {
    background: $astronaut-blue;
    padding: 1em;
    display: grid;
    align-items: center;
    @include box_shadow(2);
  }

  nav {
    grid-column-start: 2;
    align-self: center;
    justify-self: end;
    display: flex;

    a {
      margin: 1.5em 4em 0 0;
      color: $gallery;

      &:last-child {
        margin: 1.5em 0 0 0;
      }

      span {
        font-size: 1.2em;
        font-family: $font-mono;
        color: $gallery;

        &:hover {
          color: $golden-fizz;
        }
      }
    }
  }

  svg {
    display: none;
  }
}

@media (max-width: $phablet) {
  .siteName {
    display: flex;
    justify-content: center;
    background: $astronaut-blue;
    color: $gallery;
    @include box_shadow(1);
  }

  nav {
    display: flex;
    justify-content: space-between;
    padding: 0.75em 2em 0.5em;
    align-items: center;
    background-color: $white;
    @include box_shadow(2);
  }

  .navlink {
    display: flex;
    flex-direction: column;
    align-items: center;
    color: $cod-gray;
    fill: $cod-gray;

    &:hover {
      color: lighten($cod-gray, 50);
      fill: lighten($cod-gray, 50);
    }

    svg {
      margin-bottom: 0.2em;
    }
  }
}
</style>
