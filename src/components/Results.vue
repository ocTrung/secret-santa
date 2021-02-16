<template>
  <div class="results">
    <ol>
      <li v-for="person in group" :key="person.name">
        {{ person.name }}
        <!-- email: {{ person.email }} -->
      </li>
    </ol>

    <ul v-if="this.$store.state.showTest">
      <li v-for="person in group" :key="person.name">
        {{ group[person.giftee-1].name}}
      </li>
    </ul>

  </div>
</template>

<script>
  export default {
    computed: {
      group(){
        return this.$store.state.group
      },
      showTest(){
        return this.$store.state.showTest
      }
    }
  }
</script>

<style scoped>
.results {
  margin-top:24px;
  background-color: rgb(190, 149, 86);
  display: inline-block;
  padding: 20px;
  padding-left: 25%;
  padding-right: 25%;


}
ul {
  display: inline-block;
  list-style-type: none;
  font-size: 20px;
  color:rgb(170, 0, 0);
  font-weight: bold;

}
ol {
  display: inline-block;
  font-size: 20px;
  color: white;
}

</style>