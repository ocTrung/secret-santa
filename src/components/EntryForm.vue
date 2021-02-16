<template>
  <div>

    <p class="instructions">
      Enter info for each person then click 'Create Test List' when you are ready
    </p>

    <form @submit.prevent="onSubmit">
      <p>
        <label for="name" ref="startPos">Name:</label>
        <input id="name" v-model="name">
      </p>

      <p>
        <label for="email">Email:</label>
        <input id="email" v-model="email">
      </p>

      <p>
        <input type="submit" value="Add Person">
      </p>
    </form>

    <button @click="generateList">Create Test List</button>

  </div>
</template>

<script>
  export default {
    computed: {
      group(){
        return this.$store.state.group
      }
    },
    data() {
      return {
        name: null,
        email: null,
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
        })

        this.$store.state.showTest = true
      },
      onSubmit: function () {
        //create new person from v-model input
        let p = {
          name: this.name,
          email: this.email,
          gifted: 0,
        }

        this.$store.state.group.push(p)

        // reset fields 
        this.name = ""
        this.email = ""
        this.$refs.startPos.focus()
      }
    }
  }
</script>

<style lang="scss" scoped>

</style>