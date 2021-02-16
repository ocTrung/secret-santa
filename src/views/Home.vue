<template>
  <div class="home">
    <EntryForm/>
    <Results/>
  </div>
</template>

<script>
// @ is an alias to /src
import EntryForm from "@/components/EntryForm.vue";
import Results from '@/components/Results.vue';

export default {
  name: "Home",
  components: {
    EntryForm,
    Results
  }
};
</script>
