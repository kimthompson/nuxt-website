<template>
  <section id="skills" class="skills">
    <div class="skills_header">
      <h2>Skills</h2>
      <button @click="forceRerender">
        <fa :icon="faRedoAlt"/>
      </button>
    </div>
    <vue-swing ref="vueswing" :config="config" :key="componentKey">
      <div v-for="skill in skills" :key="skill.index" class="skillCard">
        <div class="skillCard_top">
          <h2 class="skillCard_rank">{{ skill.level }}</h2>
          <h3 class="skillCard_title">{{ skill.name }}</h3>
        </div>
        <fa :style="{color: skill.color}" :icon="skill.icon" class="skillCard_icon"/>
        <p class="skillCard_story" v-html="skill.story"></p>
        <div class="skillCard_bottom">
          <h3 class="skillCard_title">{{ skill.name }}</h3>
          <h2 class="skillCard_rank">{{ skill.level }}</h2>
        </div>
      </div>
    </vue-swing>
  </section>
</template>

<script>
import { skills } from '../../assets/data/skills_data.js'
import { faRedoAlt } from '@fortawesome/free-solid-svg-icons'
import VueSwing from 'vue-swing'

export default {
  components: {
    VueSwing
  },
  data() {
    return {
      skills: skills.sort(function(a, b) {
        if (a.level < b.level) return -1
        if (a.level > b.level) return 1
        return 0
      }),
      config: {
        allowedDirections: [VueSwing.Direction.LEFT, VueSwing.Direction.RIGHT],
        minThrowOutDistance: 350,
        maxThrowOutDistance: 450
      },
      componentKey: 0
    }
  },
  computed: {
    faRedoAlt() {
      return faRedoAlt
    }
  },
  methods: {
    isMobile() {
      if (
        /Android|webOS|iPhone|iPad|iPod|BlackBerry/i.test(navigator.userAgent)
      ) {
        console.log(true)
        return true
      } else {
        console.log(false)
        return false
      }
    },
    forceRerender() {
      this.componentKey += 1
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../../assets/scss/_vars.scss';
@import '../../assets/scss/_mixins.scss';

.skills {
  background-color: $mako;
  color: $gallery;
  min-height: 600px;
}

.skills_header {
  display: flex;
  justify-content: space-between;
  margin: 0 1rem;
}

.skills_container {
  display: flex;
}

.skillCard {
  width: 17em;
  height: 25em;
  background-color: $gallery;
  color: $cod-gray;
  border-radius: 1em;
  padding: 1em;
  display: grid;
  grid-template-columns: auto;
  grid-template-rows: 3.5em auto 3.5em;
  align-items: center;
  @include box_shadow(2);
  border-radius: 15px;
  justify-content: center;
  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;
  margin-top: 30px;
  position: absolute;
}

.skillCard_rank {
  font-size: 1.75em;
}

.skillCard_title {
  font-size: 1.25em;
}

.skillCard_icon {
  grid-column: 1;
  grid-row: 2;
  width: 17em;
  height: 17em;
  fill-opacity: 0.4;
}

.skillCard_story {
  grid-column: 1;
  grid-row: 2;
  color: $cod-gray;
  font-size: 1.2em;
  line-height: 1.5em;
  text-align: center;
}

.skillCard_top {
  display: flex;
  align-items: start;
  justify-content: space-between;
  grid-row: 1;
}

.skillCard_bottom {
  display: flex;
  align-items: end;
  justify-content: space-between;
  grid-row: 3;
}

@media (max-width: $tablet) {
  .skills {
    min-height: 500px;
  }

  .skillCard {
    width: 15em;
    height: 20em;
    grid-template-rows: 1.5em auto 1.5em;
    padding: 1.5em;
  }

  .skillCard_rank {
    font-size: 1.25em;
  }

  .skillCard_title {
    font-size: 1em;
  }

  .skillCard_story {
    font-size: 1.1em;
    line-height: 1.4em;
  }
}
</style>
