<template>
  <div>
    <nuxt-link to="/jokes">Back To Jokes</nuxt-link>
    <h2>{{ joke.joke }}</h2>
    <hr>
    <small>Joke ID: {{ joke.id }}</small>
    <hr>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";

@Component
export default class SingleJoke extends Vue{
  joke: object = {}
  private async asyncData({$axios, params }: any): Promise<any>{
    const response = await $axios.$get(`https://icanhazdadjoke.com/j/${params.id}`,{
      headers: {
        Accept: 'application/json'
      }
    })
    return {
      joke: response
    }
  }
}
</script>

<style>

</style>
