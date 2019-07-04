<template>
<div class="tile is-ancestor">
  <div class="tile is-vertical is-parent">
    <div class="tile is-child">
      <figure 
        class="image is-5by4"
        :class="{'is-shadow':hover}"
        @mouseover="hover = true"
        @mouseout="hover = false"
      >
        <img :src="data.imgUrl1" >
      </figure>
    </div>
  </div>
  <div class="tile is-parent">
    <div class="tile is-child">
      <p class="title is-2">{{data.title}}<p>
      <p class="has-text-justified is-size-5">{{data.text}}</p>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TileImages',
  props: [
    'data'
  ],
  data() {
    return {
      hover: false
    }
  }
}
</script>

<style sccoped>
  .is-shadow {
    box-shadow: 10px 10px 2px 2px rgba(6, 15, 34, 0.5)
  }
</style>
