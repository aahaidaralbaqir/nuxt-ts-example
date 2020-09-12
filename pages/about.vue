<template>
  <div>
    <h1>About DadJokes</h1>
    <p>This is an app that displays corny dad jokes</p>
  </div>
</template>

<script lang="ts">
import { Component,Vue } from "nuxt-property-decorator";

@Component
export default class About extends Vue {
  private head() : any{
    return {
     title: 'About the app',
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
