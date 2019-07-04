<template>
  <div class="columns">
    <div class="column" v-for="(item,i) in cardItems" :key="i">
      <div class="level">
        <div class="level-item has-text-centered">
          <figure class="image is-128x128">
            <img :src="item.image" >
          </figure>
        </div>
      </div>  
      <p class="title is-4 has-text-centered">{{item.title}}</p>
      <p class="is-size-5 has-text-centered">
        {{item.text}}
      </p>  
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cards',
  props: ['cardItems'],
  data() {
    return {
      
    }
  }

}
</script>

<style>

</style>
