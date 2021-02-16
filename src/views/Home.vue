<template>
  <div class="home">
    <EntryForm/>
  </div>
</template>

<script>
// @ is an alias to /src
import EntryForm from "@/components/EntryForm.vue";

export default {
  name: "Home",
  components: {
    EntryForm
  }
};
</script>
