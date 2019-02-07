<template>
  <footer>
    <div class="icon_buttons">
      <a class="btn_icon btn_icon-github" href="https://github.com/kimthompson">
        <fa :icon="faGithubAlt"/>
      </a>
      <a class="btn_icon btn_icon-medium" href="https://medium.com/kim-thompson">
        <fa :icon="faMediumM"/>
      </a>
      <a class="btn_icon btn_icon-codepen" href="https://codepen.io/KimicalBurn/#">
        <fa :icon="faCodepen"/>
      </a>
      <a class="btn_icon btn_icon-twitter" href="https://twitter.com/byKimThompson">
        <fa :icon="faTwitter"/>
      </a>
    </div>
    <a href="/Feb2019.pdf" class="btn_resume">Resume</a>
  </footer>
</template>

<script>
import {
  faGithubAlt,
  faMediumM,
  faCodepen,
  faTwitter
} from '@fortawesome/free-brands-svg-icons'

export default {
  computed: {
    faGithubAlt() {
      return faGithubAlt
    },
    faMediumM() {
      return faMediumM
    },
    faCodepen() {
      return faCodepen
    },
    faTwitter() {
      return faTwitter
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../assets/scss/_vars.scss';

footer {
  display: grid;
  grid-template-rows: auto auto;
  width: 100%;
  align-items: center;
  justify-items: center;
  background: $astronaut-blue;
  padding: 2em 0;
}

.icon_buttons {
  grid-row-start: 2;
  display: flex;
  justify-content: space-around;
  width: 100%;
}

.btn_icon {
  transition: background-color 0.25s ease;
  background-color: $gallery;
  border-radius: 4px;
  height: 3em;
  padding: 0.25em;

  &:hover {
    background-color: darken($gallery, 30%);
  }

  svg {
    color: $astronaut-blue;
    width: 3em;
    height: 3em;
  }
}

.btn_resume {
  font-family: $font-mono;
  font-size: 1.1em;
  background-color: $astronaut-blue;
  transition: background-color 0.25s ease;
  border: 2px solid $golden-fizz;
  border-radius: 4px;
  padding: 1em 0;
  width: 13em;
  color: $golden-fizz;
  margin-bottom: 1.5em;
  text-align: center;
  grid-row-start: 1;

  &:hover {
    background-color: lighten($astronaut-blue, 10%);
  }
}
</style>
