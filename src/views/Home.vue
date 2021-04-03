<template>
  <div class="home">
    <h1 class="title">SRO Taxi Timer [Silkroad Online]</h1>
    <p class="description">Leave this tab open while using the timer. Refreshing or closing the tab will reset all timers.</p>
    <Taxiform />
    <p class="backlink"><a href="https://www.elitepvpers.com/" target="_blank" style="color:#808080;">Elitepvpers</a></p>
  </div>
</template>

<script>
// @ is an alias to /src
import Taxiform from '../components/Taxiform.vue'

export default {
  name: 'Home',
  components: {Taxiform}
}
</script>

<style>
.title {
  font-size: 1em;
  font-weight: 700;
  color:black;
  margin:1rem 0 0rem 0;
}
.description {
  margin: 0.5rem 0 2rem 0;
}
.backlink {
  color: #808080;
  margin:60px;
}
</style>