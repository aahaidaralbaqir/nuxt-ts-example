<template>
  <div>
    <h2>
      Welcome to the best corny dad jokes on the web
    </h2>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";

@Component({
  components: {

  }
})
export default class Home extends Vue {
  private head(): any {
    return {
     title: 'Home the app',
     meta: [
       {
         hid: 'description',
         name: 'description',
         content: 'Best place for corny dad jokes'
       }
     ]
    }
  }
}
</script>

<style>
</style>
