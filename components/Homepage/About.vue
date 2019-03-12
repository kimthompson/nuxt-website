<template>
  <section id="about" class="about">
    <div class="about_right">
      <img
        class="headshot-cutout"
        src="../../assets/images/headshot.png"
        srcset="../../assets/images/headshot.png 721w, ../../assets/images/headshot@2x.png 1442w"
        alt="I should probably pay for a professional headshot someday, but for now, I thank The Beauty Lab's photography lamps."
      >
      <img
        class="headshot-square"
        src="../../assets/images/headshot_square.jpg"
        alt="I should probably pay for a professional headshot someday, but for now, I thank The Beauty Lab's photography lamps."
      >
    </div>
    <livejournal/>
    <div class="about_left">
      <h2>About Me</h2>
      <aside>I’m a software developer and writer who has been living and working in the Twin Cities since I graduated from the University of Minnesota in 2015. I'm a generalist, with experience making applications for web, Windows and iOS. I currently make web apps for Minnesota Public Radio. I hope to post my side projects here, and to blog about them and many other topics on Medium.</aside>
    </div>
  </section>
</template>

<script>
import Livejournal from './Livejournal.vue'

export default {
  components: {
    Livejournal
  }
}
</script>

<style lang='scss' scoped>
@import '../../assets/scss/_vars.scss';

.page-enter-active {
  animation: acrossIn 0.4s ease-out both;
}

.page-leave-active {
  animation: acrossOut 0.6s ease-in both;
}

.about {
  display: grid;
  justify-items: center;
  margin: 1em;

  h2 {
    justify-self: start;
  }

  aside {
    font-size: 1em;
    line-height: 1.3em;
  }
}

.headshot-cutout {
  display: none;
}

.headshot-square {
  border-radius: 50%;
  max-width: 15em;
  margin-bottom: 1em;
}

@media (min-width: $phablet) {
  .about {
    display: grid;
    grid-template-columns: 50% 50%;
    justify-items: end;
    align-items: end;
    margin: 0;

    &_left {
      align-self: start;
      grid-column-start: 1;
      grid-row-start: 1;
      margin-left: 1em;
    }

    &_right {
      grid-column-start: 2;
      grid-row-start: 1;
    }

    aside {
      font-size: 0.9em;
      line-height: 1.2em;
      margin-bottom: 1em;
    }

    .livejournal {
      grid-column-start: 2;
      grid-row-start: 1;
    }
  }

  .headshot-square {
    display: none;
  }

  .headshot-cutout {
    display: block;
  }
}

@media (min-width: $tablet) {
  .about {
    aside {
      font-size: 1.3em;
      line-height: 1.4em;
    }
  }
}

@media (min-width: $laptop) {
  .about {
    grid-template-columns: 65% 35%;

    h2 {
      margin-top: 1em;
      margin-bottom: 1em;
    }

    aside {
      font-size: 1.5em;
      line-height: 1.6em;
    }
  }
}
</style>
