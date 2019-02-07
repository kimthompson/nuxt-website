<template>
  <div>
    <nuxt/>
  </div>
</template>

<style lang='scss'>
@import '../assets/scss/_vars.scss';

* {
  font-family: $font-sans;
  margin: 0;
  padding: 0;
  max-width: 100%;
}

body {
  background-color: $gallery;
}

a {
  text-decoration: none;
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: $font-handwriting;
}

h1 {
  font-size: 5vw;
}

h2 {
  font-size: 4vw;
}

@media (min-width: $laptop) {
  h1 {
    font-size: 3vw;
  }

  h2 {
    font-size: 2vw;
  }
}

ul,
ol,
li {
  font-family: $font-mono;
  list-style-type: none;
}

aside {
  font-family: $font-mono;
}

button,
input[type='submit'],
input[type='reset'] {
  background: none;
  color: inherit;
  border: none;
  padding: 0;
  font: inherit;
  cursor: pointer;
  outline: inherit;
}
</style>
