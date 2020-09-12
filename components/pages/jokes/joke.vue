<template>
 <nuxt-link :to="link">
  <div class="joke">
    <p>{{ joke }}</p>
  </div>
 </nuxt-link>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "nuxt-property-decorator";

@Component
export default class Joke extends Vue {
  @Prop(String) readonly joke!: string
  @Prop(String) readonly id!: string

  link: string = `jokes/${this.id}`
}
</script>

<style scoped>
  .joke {
    padding: 1rem;
    border: 1px solid #ccc;
    margin: 1rem 0;
  }
</style>
