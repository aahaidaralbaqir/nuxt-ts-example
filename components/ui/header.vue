<template>
  <header class="header">
    <h1 class="title">Dad Jokes</h1>
    <ul>
      <li>
        <nuxt-link to="/">Home</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/jokes">Jokes</nuxt-link>
      </li>
       <li>
        <nuxt-link to="/about">About</nuxt-link>
      </li>
    </ul>
  </header>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator';
@Component({
  name: 'UiHeader'
})
export default class Header extends Vue{
}
</script>

<style scoped>
 .header{
   display: flex;
   justify-content: space-between;
   align-items: center;
   margin-bottom: 1rem;
   padding-bottom: 1rem;
   border: 1px solid #ccc;
 }
 .header .title {
   font-size: 3rem;
   color: #524688;
 }
.header ul {
  display: flex;
}
.header ul li {
  color: white;
  list-style: none;
}
.header a{
  display: inline-block;
  background: #333;
  color: #fff;
  padding: 0.3rem 1rem;
  margin-right: 0.5rem;
}
</style>
