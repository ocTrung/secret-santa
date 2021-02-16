<template>
  <div>
    <p>
      <label for="name">Name:</label>
      <input id="name" v-model="name">
    </p>

    <p>
      <label for="email">Email:</label>
      <input id="email" v-model="email">
    </p>

    <button @click="generateList">
      Generate List
    </button>

    <ul>
      <li v-for="person in group" :key="person.name">
        name: {{ person.name }}
        email: {{ person.email }}
        giftee: {{ allGifted ? group[person.giftee-1].name : "unassigned"}}
      </li>
    </ul>

  </div>
</template>

<script>
  export default {
    data() {
      return {
        email: null,
        name: null,
        group: [],
        allGifted: false,
      }
    },
    methods: {
      generateList: function () {
        let picked = []
        let size = this.group.length

        this.group.forEach(person => {
          let pick = Math.floor( Math.random() * size) + 1

          while (picked.includes(pick) || pick-1 === this.group.indexOf(person))
            pick = Math.floor( Math.random() * size) + 1

          picked.push(pick)
          person.giftee = pick
          console.log("person: " + person)
        })

        console.log(this.group)
        this.allGifted = true
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>