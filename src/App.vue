<template>
  <div>
    <h1>Softhouse</h1>
    <div v-for="paragraph in paragraphs" :key="paragraph.id">
      <h2>{{ paragraph.header }}</h2>
      <p>{{ paragraph.content }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      paragraphs: "",
    };
  },
  async mounted() {
    const body = await (
      await fetch(
        "https://cosmosdbfunctionapp20220423133227.azurewebsites.net/api/page/1"
      )
    ).json();
    this.paragraphs = body;
  },
};
</script>
