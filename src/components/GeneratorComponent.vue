<template>
  <div>
    <p>Name: <input v-model="name"></p>
    <p>Size: <input v-model="size"></p>
    <p>desc: <input v-model="desc"></p>
    <p>oil? <input type="checkbox" v-model="oil"></p>
    <pre><code>
{{code}}
    </code></pre>
  </div>
</template>

<script>
export default {
  data(){
    return {
      name: "painting_file_name",
      size: "10x9",
      desc: "painting description",
      oil: true,
    }
  },
  computed:{
    code(){
      return `
<figure>
  <a href="public/images/${this.type}/${this.name}_slide.jpg" data-lightbox="image" data-title="${this.desc} - ${this.size}" data-alt="${this.desc}">
    <img class="gallery_image" src="public/images/${this.type}/${this.name}_small.jpg" alt="${this.desc}">
  </a>
  <figcaption>
    ${this.desc}
  </figcaption>
</figure>
`
    },
    type(){
      return this.oil ? "oil" : "watercolour";
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
