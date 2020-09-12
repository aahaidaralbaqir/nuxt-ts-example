<template>
  <section>
  <Search
    @search="handleSearch"
  />
  <Joke
    v-for="joke in jokes"
    :key="joke.id"
    :id="joke.id"
    :joke="joke.joke"
  />
  </section>
</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";
import Joke from "~/components/pages/jokes/joke.vue"
import Search from "~/components/ui/search.vue";
interface IJoke {
  id: string
  joke: string
}
@Component({
  components: {
    Joke,
    Search
  }
})
export default class Jokes extends Vue{

  jokes: Array<IJoke> = []

  private async asyncData({$axios}: any): Promise<any> {
    const response = await $axios.$get("https://icanhazdadjoke.com/search",{
      headers: {
        Accept: 'application/json'
      }
    })
    return {
      jokes: response.results
    }
  }
  private async  handleSearch(text: any) : Promise<void> {
    this.jokes = this.jokes.filter(item => item.joke.toLowerCase().match(text))
  }
}
</script>

<style>

</style>
