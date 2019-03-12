<template>
  <section :class="['livejournal', elementClass]">
    <table>
      <tr class="livejournal_data">
        <td class="livejournal_label">currently reading</td>
        <td class="livejournal_attr">The Handmaid's Tale</td>
      </tr>
      <tr>
        <td class="livejournal_label">currently playing</td>
        <td class="livejournal_attr">Final Fantasy X</td>
      </tr>
      <tr>
        <td class="livejournal_label">currently watching</td>
        <td class="livejournal_attr">RuPaul's Drag Race s11</td>
      </tr>
      <tr>
        <td class="livejournal_label">currently playing (mmo edition)</td>
        <td class="livejournal_attr">Final Fantasy XIV</td>
      </tr>
      <tr>
        <td class="livejournal_label">currently watching (anime edition)</td>
        <td class="livejournal_attr">Love Is War</td>
      </tr>
    </table>
  </section>
</template>

<script>
export default {
  props: {
    elementClass: {
      type: String,
      default: '',
      required: false
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../../assets/scss/_vars.scss';

.livejournal {
  display: none;
}

@media (min-width: $phablet) {
  .livejournal {
    display: block;
    clip-path: polygon(15% 0, 100% 0%, 100% 100%, 0% 100%);
    -webkit-clip-path: polygon(15% 0, 100% 0%, 100% 100%, 0% 100%);
    background-color: $golden-fizz;
    font-size: 0.5em;
    width: 100%;
    align-self: end;
    margin-bottom: 1em;

    table {
      margin-left: 1em;
      margin-right: 1em;
    }

    &_label {
      font-family: $font-mono;
      text-align: right;
      color: $astronaut-blue;
      vertical-align: top;
    }

    &_attr {
      font-family: $font-mono;
      text-align: left;
      font-weight: bold;
      color: $cod-gray;
      padding-left: 0.25em;
      vertical-align: top;
    }
  }
}

@media (min-width: $tablet) {
  .livejournal {
    font-size: 0.6em;
  }
}

@media (min-width: $desktop) {
  .livejournal {
    font-size: 0.85em;
  }
}
</style>
