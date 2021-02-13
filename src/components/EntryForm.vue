<template>
  <div>
        <form class="review-form" @submit.prevent="onSubmit">
      <p>
        <label for="name">Name:</label>
        <input id="name" v-model="name" placeholder="name">
      </p>
      
      <p>
        <label for="email">Email:</label>      
        <textarea id="email" v-model="email"></textarea>
      </p>
          
      <p>
        <input type="submit" value="Submit">  
      </p>    
    
    </form>

  </div>
</template>

<script>
  export default {
    data() {
      return {
      name: null,
      email: null,
      }
    },
    methods: {
      submitForm(){
        axios.post(/, this.form)
          .then((res) => {

          })
          .catch((error) => {

          }).finally(() => {
            
          })
      }
    }

    
  }
</script>

<style lang="scss" scoped>

</style>