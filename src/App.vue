<template>
  <div id="app">
    <FirstSection />
    <ThirdSection />
    <SecondSection />
    <FourthSection />
    <FifthSection />
  </div>
</template>

<script>
import FirstSection from './components/FirstSection.vue'
import SecondSection from './components/SecondSection.vue'
import ThirdSection from './components/ThirdSection.vue'
import FourthSection from './components/FourthSection.vue'
import FifthSection from './components/FifthSection.vue'

export default {
  name: 'App',
  components: {
    FirstSection,
    SecondSection,
    ThirdSection,
    FourthSection,
    FifthSection
  }
}
</script>

<style lang="scss">
@import "@/assets/sass/style";

html,
*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 16px;
}

@media screen and (max-width: 768px) {
  #app {
    overflow-x: hidden;
  }
  
}
</style>
