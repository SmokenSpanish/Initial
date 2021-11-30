<template>
  <div class="finder">
      <h1 class="finder__title">Я найду тебя!</h1>
      <input type="text" @input="searchText = $event.target.value">
      <p class="finder__text">Всего имен:{{ ` ${names.length}` }}</p> 
      <p class="finder__text">Всего совпадений:{{ getFilteredNames.length }}</p>
  </div>
<ul>
    <li v-for="(name, index) in getFilteredNames" :key="index">
        {{ name }}
    </li>
</ul>
</template>

<script>
export default {
    data() {
        return {
            searchText: '',
            names: ['Василий', 'Николай', 'Максим', 'Раф', 'Зинаида']
        }
    },
    computed: {
        getFilteredNames() {
            return this.names.filter(name => name.toLowerCase().includes(this.searchText.toLowerCase()))
        }
    }
    
}
</script>

<style>
    .finder__text {
        display: inline-block;
        margin-right: 20px;
    }
</style>