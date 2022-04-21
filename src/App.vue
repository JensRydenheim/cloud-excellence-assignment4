<template>
  <div>Message from API: {{ message }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "",
    };
  },
  async mounted() {
    const { body } = await (await fetch("/api/content?name=Softhouse")).json();
    this.message = body;
  },
};
</script>
