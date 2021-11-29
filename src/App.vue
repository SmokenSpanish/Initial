<template>
  <div id="app">
<MyComponent/>
<Counter/>
<ProfileCard/>
<Finder/>
  </div>
</template>

<script>
import MyComponent from './components/MyComponent';
import Counter from './components/Counter';
import ProfileCard from './components/ProfileCard';
import Finder from './components/Finder';

export default {
  name: 'App',
  components: {
    MyComponent,
    Counter,
    ProfileCard,
    Finder
  }
}
</script>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;

body {
  margin: 0;
}

  }

</style>
