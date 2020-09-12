<template>
  <div>
    <input type="text" v-model="text" @keyup.enter="handleClickSearch" />
    <button @click="handleClickSearch">search</button>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Emit } from "nuxt-property-decorator";
@Component({
  name: "UiHeader"
})
export default class Search extends Vue {
  text: string = "";

  @Emit("search")
  private handleClickSearch(text: string) {
    return this.text
  }
}
</script>

<style>

</style>
