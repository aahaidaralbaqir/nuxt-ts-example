<template>
  <div class="container">
    <ui-header />
    <Nuxt />
  </div>
</template>
<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";
import UiHeader from "~/components/ui/header.vue"
@Component({
  components: {
    UiHeader
  }
})
export default class DefaultLayout extends Vue {

}
</script>
<style>
body {
  background-color: #eee;
  font-size: 1rem;
  line-height: 1.6;
  background: #f4f4f4;
}
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  a {
    text-decoration: none;
    color: #ccc;
  }
  .container {
    max-width: 80%;
    margin: 2rem auto;
    overflow:hidden;
    padding: 1rem 2rem;
    background: #fff;
  }
</style>

