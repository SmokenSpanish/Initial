<template>
  <div class="finder">
      <h1 class="finder__title">Я найду тебя!</h1>
      <input type="text">
      <p class="finder__text">Всего имен:{{ ` ${names.length}` }}</p> 
      <p class="finder__text">Всего совпадений:</p>
  </div>
<ul>
    <li :value="names">
        {{  }}
    </li>
</ul>
</template>

<script>
export default {
    data() {
        return {
            names: ['Василий', 'Николай', 'Максим', 'Раф']
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